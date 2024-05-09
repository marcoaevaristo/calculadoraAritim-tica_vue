<template>
  <div id="app">
    <MinhaCalculadora />
  </div>
</template>

<script>
import MinhaCalculadora from './components/CalculadoraComponent.vue';

export default {
  name: 'App',
  components: {
    MinhaCalculadora,
  },
};
</script>

<style scoped>
/* Estilos para a página principal */
#app {
  text-align: center;
  font-family: Avenir, Helvetica, Arial, sans-serif;
  color: #333;
  padding: 20px;
}
</style>
