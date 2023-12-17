<!-- src/App.vue -->

<template>
    <div id="app">
        <Conversor moeda-a="USD" moeda-b="BRL"></Conversor>
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
            moedaA: 'USD', // Substitua pelos valores desejados
            moedaB: 'EUR', // Substitua pelos valores desejados
        };
    },
};
</script>

<style>
#app {
    font-family: Avenir, Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
    margin-top: 60px;
}
</style>
