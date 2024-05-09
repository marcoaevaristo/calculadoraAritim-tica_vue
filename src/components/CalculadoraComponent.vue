<template>
  <div class="calculadora">
    <h2>Calculadora Aritmética</h2>
    <div class="input-group">
      <label for="num1">Número 1:</label>
      <input type="number" id="num1" v-model.number="num1" @input="calcular" />
    </div>
    <div class="input-group">
      <label for="num2">Número 2:</label>
      <input type="number" id="num2" v-model.number="num2" @input="calcular" />
    </div>
    <div class="input-group">
      <label for="operacao">Operação:</label>
      <select id="operacao" v-model="operacao" @change="calcular">
        <option value="add">Adicionar</option>
        <option value="subtract">Subtrair</option>
        <option value="multiply">Multiplicar</option>
        <option value="divide">Dividir</option>
      </select>
    </div>
    <div class="resultado">
      <strong>Resultado:</strong> {{ resultado }}
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      num1: 0,
      num2: 0,
      operacao: 'add',
      resultado: 0,
    };
  },
  methods: {
    calcular() {
      switch (this.operacao) {
        case 'add':
          this.resultado = this.num1 + this.num2;
          break;
        case 'subtract':
          this.resultado = this.num1 - this.num2;
          break;
        case 'multiply':
          this.resultado = this.num1 * this.num2;
          break;
        case 'divide':
          this.resultado = this.num2 !== 0 ? this.num1 / this.num2 : 'Divisão por zero';
          break;
        default:
          this.resultado = 0;
          break;
      }
    },
  },
};
</script>

<style scoped>
/* Estilos para a calculadora */
.calculadora {
  background-color: #f5f5f5;
  padding: 20px;
  border-radius: 10px;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
  display: flex;
  flex-direction: column;
  gap: 15px;
}

.input-group {
  align-items: center;
}

.input-group label {
  font-weight: bold;
  margin-right: 10px;
}

.input-group input,
.input-group select {
  padding: 8px;
  border: 1px solid #ccc;
  border-radius: 5px;
  transition: all 0.3s ease;
}

.input-group input:focus,
.input-group select:focus {
  border-color: #3498db;
  box-shadow: 0 0 5px rgba(52, 152, 219, 0.3);
}

.resultado {
  font-weight: bold;
}
</style>

