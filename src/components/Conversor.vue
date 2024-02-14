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
    width: 100%;
    box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.2);
    border: 1px solid #c2c2c2;
    overflow: hidden;
    display: flex;
    align-items: center;
    flex-direction: column;
    justify-content: center;
    gap: 1vw;
    border-radius: 5px;
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
    .conversor h2 {
        font-size: 3.1vw;
        width: 100%;
    }
    #input-name {
        width: 100%;
    }
    .conversor {
        padding: 2%;
        width: 100%;
        box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.2);
        border: 1px solid #c2c2c2;
        overflow: hidden;
        gap: 2vw;
        display: flex;
        align-items: center;
        flex-direction: column;
        justify-content: center;
    }

    .conversor input {
        width: 100%;
        height: 6vw;
        padding-block: 0;
        padding-inline: 0;
        overflow: hidden;
        display: flex;
        align-content: center;
        justify-content: center;
    }
}
</style>
