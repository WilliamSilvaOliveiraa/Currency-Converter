<!-- src/App.vue -->

<template>
    <h1 class="text-center">Conversor de Moedas</h1>
    <div class="linha">
        <Conversor
            :moedaA="moedaA"
            :moedaB="moedaB"
            :cotacao="cotacaoReaisToDolar"
        ></Conversor>

        <Conversor
            :moedaA="moedaB"
            :moedaB="moedaA"
            :cotacao="cotacaoDolarToReais"
        ></Conversor>
    </div>
    <div class="linha">
        <Conversor
            :moedaA="moedaA"
            :moedaB="moedaC"
            :cotacao="cotacaoReaisToDolarCad"
        ></Conversor>

        <Conversor
            :moedaA="moedaC"
            :moedaB="moedaA"
            :cotacao="cotacaoDolarCadToReais"
        ></Conversor>
    </div>
    <div class="linha">
        <Conversor
            :moedaA="moedaA"
            :moedaB="moedaD"
            :cotacao="cotacaoReaisToEuro"
        ></Conversor>

        <Conversor
            :moedaA="moedaD"
            :moedaB="moedaA"
            :cotacao="cotacaoEuroToReais"
        ></Conversor>
    </div>
</template>

<script>
import Conversor from './components/Conversor.vue';

export default {
    name: 'App',
    components: {
        Conversor,
    },
    data() {
        return {
            moedaA: 'BRL', // Substitua pelos valores desejados
            moedaB: 'USD', // Substitua pelos valores desejados
            moedaC: 'CAD', // Substitua pelos valores desejados
            moedaD: 'EUR', // Substitua pelos valores desejados

            cotacaoDolarToReais: 4.94,
            cotacaoReaisToDolar: 0.2, // Defina outro valor de cotação
            cotacaoDolarCadToReais: 3.7, // Defina outro valor de cotação
            cotacaoReaisToDolarCad: 0.27, // Defina outro valor de cotação
            cotacaoReaisToEuro: 0.19, // Defina outro valor de cotação
            cotacaoEuroToReais: 5.39, // Defina outro valor de cotação
        };
    },
};
</script>

<style>
#app {
    max-width: 100%;
    font-family: Avenir, Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    margin-bottom: 100px;
    color: #2c3e50;
    margin-top: 0.5vw;
    height: 100%;
    overflow: hidden;
    padding: 0 25%;
}
.linha {
    margin-top: 40px;
    display: flex;
    justify-content: space-between;
    width: 100%;
    gap: 3vw;
}
.text-center {
    text-align: center;
    font-size: 2.5vw;
}

@media screen and (max-width: 767px) {
    #app {
        max-width: 100%;
        font-family: Avenir, Helvetica, Arial, sans-serif;
        -webkit-font-smoothing: antialiased;
        -moz-osx-font-smoothing: grayscale;
        margin-bottom: 0;
        color: #2c3e50;
        margin-top: 10vw;
        height: 100%;
        overflow: hidden;
        padding: 0 5%;
    }
    .text-center {
        text-align: center;
        font-size: 4vw;
    }
}
</style>
