<template>
  <div id="app">
    <h1>Teclat de Calculadora</h1>
    <div class="calculator">
      <button v-for="number in numbers" :key="number" @click="showNumber(number)">
        {{ number }}
      </button>
    </div>
    <div class="output">
      <p>{{ clickedNumber }}</p>
    </div>
  </div>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      numbers: [1, 2, 3, 4, 5, 6, 7, 8, 9],
      clickedNumber: null,
    };
  },
  methods: {
    showNumber(number) {
      this.clickedNumber = `Has clicat el número: ${number}`;
    },
  },
};
</script>

<style scoped>
.calculator {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 10px;
}

button {
  padding: 20px;
  font-size: 20px;
  cursor: pointer;
}

button:hover {
  background-color: #f0f0f0;
}

.output {
  margin-top: 20px;
  font-size: 24px;
  font-weight: bold;
}
</style>
