<template>
  <div class="calculator">
    <h1>Calculadora Aritmética</h1>
    <div>
      <input v-model="num1" type="number" placeholder="Número 1" @input="calculate" />
      <select v-model="operator" @change="calculate">
        <option value="+">+</option>
        <option value="-">-</option>
        <option value="*">*</option>
        <option value="/">/</option>
      </select>
      <input v-model="num2" type="number" placeholder="Número 2" @input="calculate" />
      <div class="result">{{ result }}</div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      num1: 0,
      num2: 0,
      operator: "+",
      result: 0,
    };
  },
  methods: {
    calculate() {
      switch (this.operator) {
        case "+":
          this.result = this.num1 + this.num2;
          break;
        case "-":
          this.result = this.num1 - this.num2;
          break;
        case "*":
          this.result = this.num1 * this.num2;
          break;
        case "/":
          this.result = this.num1 / this.num2;
          break;
      }
    },
  },
};
</script>

<style scoped>
.calculator {
  display: flex;
  flex-direction: column;
  align-items: center;
  margin-top: 50px;
}

input,
select {
  margin: 10px;
  padding: 5px;
}

.result {
  margin-top: 20px;
  font-size: 24px;
}
</style>
