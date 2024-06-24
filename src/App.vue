<script setup>
import { reactive } from "vue";
import Form from "./componetes/Form.vue";

const estado = reactive({
    filtro: "multiplicacao",
    numero1: 0,
    numero2: 0,
});

const multiplicacao = ({ numero1, numero2 } = estado) => {
  return numero1 * numero2;
};

const adicao = ({ numero1, numero2 } = estado) => {
    return Number(numero1 + numero2);
};

const subtracao = ({ numero1, numero2 } = estado) => {
    return numero1 - numero2;
};

const divisao = ({ numero1, numero2 } = estado) => {
    return numero1 / numero2;
};

const matematica = () => {
    const { numero1, numero2, filtro } = estado;

if ((numero1, numero2)) {
    switch (filtro) {
        case "multiplicacao":
        return multiplicacao();
        case "adicao":
        return adicao();
        case "subtracao":
        return subtracao();
        case "divisao":
        return divisao();
    }
}
};
</script>

<template>
    <div class="container">
        <header>
        <h1>Operações Matemáticas</h1>
        <p>Digite os Numeros</p>
    </header>
    <Form
        :trocar-filtro="(event) => (estado.filtro = event.target.value)"
        :valor-numero1="(event) => (estado.numero1 = Number(event.target.value))"
        :valor-numero2="(event) => (estado.numero2 = Number(event.target.value))"
    />

    <p>O resultado é {{ matematica() }}</p>
</div>
</template>

<style scoped>

#app{
    display: flex;
    align-items: center;
    justify-content: center
}
</style>