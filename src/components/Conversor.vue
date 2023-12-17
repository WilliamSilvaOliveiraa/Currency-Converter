<template>
    <div class="conversor">
        <h2>{{ moedaA }} Para {{ moedaB }}</h2>
        <input type="text" />
        <input type="button" value="Converter" />
    </div>
</template>

<script>
export default {
    name: 'ConversorComponent',
    props: ['moedaA', 'moedaB'],
};
</script>

<style scoped>
/* prettier-ignore */
</style>
