<template>
  <div id="app">
    <ArithmeticCalculator /> <!-- Incluindo nosso componente -->
  </div>
</template>

<script>
import ArithmeticCalculator from './components/ArithmeticCalculator.vue';

export default {
  components: {
    ArithmeticCalculator, // Registrando o componente
  },
};
</script>

<style>
#app {
  text-align: center;
  padding-top: 50px;
}
</style>

<style>
/* Estilos para a página principal */
#app {
  text-align: center;
  font-family: Avenir, Helvetica, Arial, sans-serif;
  font-size: 20px;
}
</style>
