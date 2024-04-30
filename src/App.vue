<script setup>
import Cabecalho from '../src/components/Cabecalho.vue';
import Calculadora from '../src/components/Calculadora.vue';
</script>

<template>
  <div class="container">
    <Cabecalho/>
    <Calculadora/>
  </div>
</template>

<style scoped>
  .container {
    display: flex;
    flex-direction: column;
    margin: auto;
    align-items: center;
  }
</style>