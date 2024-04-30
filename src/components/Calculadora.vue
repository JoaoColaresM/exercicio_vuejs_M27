<script setup>
import { reactive } from 'vue';

const estado = reactive({
    primeiroNumero: '',
    segundoNumero: '',
    operacoes: {
        soma: (x, y) => x + y,
        subtracao: (x, y) => x - y,
        multiplicacao: (x, y) => x * y,
        divisao: (x, y) => (y !== 0 ? x / y : 'Divisão por zero'),
    },
    resultado: 0,
});

const calcularResultado = () => {
    const { primeiroNumero, segundoNumero, operacaoMatematica } = estado;
    estado.resultado = estado.operacoes[operacaoMatematica](parseFloat(primeiroNumero), parseFloat(segundoNumero));
};
</script>

<template>
    <div class="calculadora">
        <input type="text" v-model="estado.primeiroNumero" @input="calcularResultado" />
        <input type="text" v-model="estado.segundoNumero" @input="calcularResultado" />

        <select v-model="estado.operacaoMatematica" @change="calcularResultado">
            <option value="soma">Soma</option>
            <option value="subtracao">Subtração</option>
            <option value="multiplicacao">Multiplicação</option>
            <option value="divisao">Divisão</option>
        </select>

        <p>Resultado: {{ estado.resultado }}</p>
    </div>
</template>

<style scoped>
    .calculadora {
        font-size: large;
        color: whitesmoke;
    }
</style>