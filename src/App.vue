<script setup>
  import Calculator from "./components/calculator.vue";
</script>

<template>
  <div class="container">
    <h1 class="mb-4 text-center">Calculadora</h1>
    <Calculator />
  </div>
</template>

<style>
:root {
  --white: #fff;

  --gray-700: #29292e;
  --gray-900: #121214;
}

* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

body {
  background-color: var(--gray-900);
  color: var(--white);
}

.container {
  background-color: var(--gray-700);

  max-width: 640px;
  padding: 2rem;

  border-radius: 8px;

  margin: 3rem auto;
}
</style>
