<script setup>
import TheCalculator from '../components/TheCalculator.vue'
</script>

<template>
  <header>
    <h3>Calculadora Aritmética</h3>
    <ul>
      <li>
        <a href="https://github.com/pedrohenrique11/calculadora_aritmetica"><img src="../assets/icons8-github.svg" alt=""></a>
      </li>
      <li>
        <a href="https://www.linkedin.com/in/pedro-henrique-79483b19a/"><img src="../assets/icons8-linkedin.svg" alt=""></a>
      </li>
    </ul>
  </header>
  <main>
    <TheCalculator />
  </main>
</template>

<style>
 header {
  display:flex;
  justify-content: space-between;
  align-items: center;

  margin: 4rem auto 0 auto;
  color: #fff;
  font-weight: 600;

  max-width: 400px;

  border-bottom: 1px solid #41b883;
 }
 img {
  width: 30px;
  margin-left: 5px;
 }
 a {
  padding: 0;
 }
 ul {
  display: flex;
  list-style: none;
 }
</style>