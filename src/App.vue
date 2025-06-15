<template>
  <div>
    <h1>Calculadora Aritmética</h1>

    <div>
      <label>Primeiro Número:</label>
      <input type="number" v-model.number="number1" />
    </div>

    <div>
      <label>Operação:</label>
      <select v-model="operation">
        <option value="add">Adição</option>
        <option value="subtract">Subtração</option>
        <option value="multiply">Multiplicação</option>
        <option value="divide">Divisão</option>
      </select>
    </div>

    <div>
      <label>Segundo Número:</label>
      <input type="number" v-model.number="number2" />
    </div>

    <div>
      <h2>Resultado: {{ result }}</h2>
    </div>
  </div>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      number1: 0,
      number2: 0,
      operation: "add"
    };
  },
  computed: {
    result() {
      switch (this.operation) {
        case "add":
          return this.number1 + this.number2;
        case "subtract":
          return this.number1 - this.number2;
        case "multiply":
          return this.number1 * this.number2;
        case "divide":
          return this.number1 / this.number2;
        default:
          return 0;
      }
    }
  }
};
</script>
