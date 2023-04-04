<template>
  <div class="calculator">
    <input v-model="num1" type="number">
    <select v-model="operator">
      <option value="+">+</option>
      <option value="-">-</option>
      <option value="*">*</option>
      <option value="/">/</option>
    </select>
    <input v-model="num2" type="number">
    <p>Result: {{ result }}</p>
  </div>
</template>

<script>
export default {
  data() {
    return {
      num1: 0,
      num2: 0,
      operator: '+'
    }
  },
  computed: {
    result() {
      switch (this.operator) {
        case '+':
          return parseInt(this.num1) + parseInt(this.num2)
        case '-':
          return parseInt(this.num1) - parseInt(this.num2)
        case '*':
          return parseInt(this.num1) * parseInt(this.num2)
        case '/':
          return parseInt(this.num1) / parseInt(this.num2)
        default:
          return 0
      }
    }
  }
}
</script>

<style lang="scss" scoped>

.calculator {
  display: flex;
  align-items: center;
  justify-content: center;
  flex-direction: column;
  height: 100vh;
  max-width: 600px;
  margin: 0 auto;
  border: 1px solid #333;
  input, select {
    margin-right: 10px;
    padding: 10px;
    font-size: 16px;
    border-radius: 5px;
    border: none;
    background-color: #f5f5f5;
    color: #333;
  }

  select {
    margin-left: -10px;
  }

  p {
    margin-top: 10px;
    font-size: 20px;
    font-weight: bold;
  }
}
</style>