<template>
    <div class="conversor">
        <h2>{{ moedaA }} Para {{ moedaB }}</h2>
        <input
            id="input-name"
            type="text"
            v-model="moedaA_value"
            v-bind:placeholder="moedaA"
        />
        <input type="button" value="Converter" v-on:click="converter" />
        <h2>{{ moedaB_value }}</h2>
    </div>
</template>

<script>
export default {
    name: 'ConversorComponent',
    props: ['moedaA', 'moedaB', 'cotacao'],
    data() {
        return {
            moedaA_value: '',
            moedaB_value: 0,
        };
    },
    methods: {
        converter() {
            const valorMoedaA = parseFloat(this.moedaA_value);
            if (isNaN(valorMoedaA)) {
                return;
            }

            // Agora, a variável 'cotacao' é uma propriedade configurável pelo componente pai
            this.moedaB_value = (valorMoedaA * this.cotacao).toFixed(2);
        },
    },
};
</script>

<style scoped>
.conversor {
    padding: 2%;
    max-width: 100%;
    box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.2);
    border: 1px solid #c2c2c2;
    overflow: hidden;
}

.conversor input {
    width: 100%;
    padding: 0;
    padding-block: 0;
    padding-inline: 0;
    overflow: hidden;
}

#input-name {
    width: 100%;
}

.conversor h2 {
    font-size: 1.4vw;
    width: 100%;
}

@media screen and (max-width: 767px) {
}
</style>
