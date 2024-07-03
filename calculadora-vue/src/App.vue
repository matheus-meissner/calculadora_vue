<script>
export default {
  data() {
    return {
      number1: 0,
      number2: 0,
      operation: 'add',
    };
  },
  computed: {
    result() {
      switch (this.operation) {
        case 'add':
          return this.number1 + this.number2;
        case 'subtract':
          return this.number1 - this.number2;
        case 'multiply':
          return this.number1 * this.number2;
        case 'divide':
          return this.number2 !== 0 ? this.number1 / this.number2 : 'Erro: Divisão por zero';
        default:
          return 0;
      }
    },
  },
};
</script>

<template>
  <div id="app">
    <h1>Calculadora Aritmética</h1>
    <div class="calculator">
      <input v-model.number="number1" type="number" placeholder="Número 1" />
      <select v-model="operation">
        <option value="add">+</option>
        <option value="subtract">-</option>
        <option value="multiply">*</option>
        <option value="divide">/</option>
      </select>
      <input v-model.number="number2" type="number" placeholder="Número 2" />
      <p>Resultado: {{ result }}</p>
    </div>
  </div>
</template>

<style>
#app {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  font-family: Avenir, Helvetica, Arial, sans-serif;
  text-align: center;
}

.calculator {
  display: flex;
  flex-direction: column;
  align-items: center;
}

input {
  margin: 5px;
  padding: 10px;
  font-size: 1em;
}

select {
  margin: 5px;
  padding: 10px;
  font-size: 1em;
}

p {
  margin: 20px;
  font-size: 1.5em;
  font-weight: bold;
}
</style>
