<script setup>
import CalculatorView from './views/CalculatorView.vue';
</script>

<template>
  <header>
      <h1>Calculadora</h1>
  </header>
  <CalculatorView />
</template>

<style scoped>
 header {
  display: flex;
  justify-content: center;
  border-bottom: 2px solid #fff;
  min-width: 20rem;

  margin-bottom: 4rem;
 }
</style>
