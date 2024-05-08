<template>
    <h1>Calculadora Aritimética</h1>
    <div class="calculator">
      <div class="calculator-display">{{ display }}</div>
      <div class="calculator-buttons">
        <!-- Botões numéricos -->
        <button v-for="num in numbers" :key="num" @click="appendNumber(num)">
          {{ num }}
        </button>
        <!-- Botões de operações -->
        <button v-for="op in operations" :key="op" @click="appendOperation(op)">
          {{ op }}
        </button>
        <!-- Botão de limpar -->
        <button @click="clearDisplay">C</button>
        <!-- Botão de resultado -->
        <button @click="calculateResult">=</button>
      </div>
    </div>
  </template>
  
  <script>
  export default {
    name: 'CalculatorComponent',
    data() {
      return {
        display: '', // Para mostrar os números e operações
        numbers: [1, 2, 3, 4, 5, 6, 7, 8, 9, 0], // Números para os botões
        operations: ['+', '-', '*', '/'], // Operações
      };
    },
    methods: {
      appendNumber(num) {
        this.display += num; // Adiciona número ao display
      },
      appendOperation(op) {
        this.display += ` ${op} `; // Adiciona operação ao display
      },
      clearDisplay() {
        this.display = ''; // Limpa o display
      },
      calculateResult() {
        try {
          this.display = eval(this.display).toString(); // Avalia e exibe resultado
        } catch (error) {
          this.display = 'Erro'; // Se erro, mostra "Erro"
        }
      },
    },
  };
  </script>
  
  <style scoped>
  .calculator {
    background-color: rgb(147, 236, 236);
    border: 2px solid #333;
    border-radius: 10px;
    padding: 20px;
    max-width: 300px;
    margin: auto;
    text-align: center;
  }
  
  .calculator-display {
    font-size: 24px;
    background: #f9f9f9;
    padding: 10px;
    border: 1px solid #ddd;
    border-radius: 5px;
    margin-bottom: 10px;
    text-align: right;
  }
  
  .calculator-buttons {
    display: grid;
    grid-template-columns: repeat(4, 1fr); 
    gap: 10px;
  }
  
  button {
    padding: 10px;
    background-color: #4CAF50;
    color: white;
    border: none;
    border-radius: 5px;
    cursor: pointer;
  }
  
  button:hover {
    background-color: #45a049;
  }
  </style>