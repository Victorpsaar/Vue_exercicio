<script setup>
  import { reactive } from 'vue'

  const state = reactive({
    firstNum: '',
    secondNum: '',
    operation: {
      soma: (a, b) => a + b,
      sub: (a, b) => a - b,
      multi: (a, b) => a * b,
      divi: (a, b) => (a && b !== 0 ? a / b : 'Error'),
      poten: (a, b) => a ** b,
      radi: (a, b) => a ** ( 1 / b )
    },
    operationNum: '1',
    result: 'Resultado:',
  })

  function calc() {
    
    const { firstNum, secondNum, operationNum } = state

    if (operationNum && firstNum && secondNum !== undefined){
      state.result = `Resultado: ${state.operation[operationNum](firstNum, secondNum)}`
    } else {
      if (firstNum === null || NaN ) {
        state.result = 'Resultado:'
      } else {
        state.result = 'Resultado:'
      }
    }
  }

</script>

<template>
  <form>
    <div class="row mb-3">
      <div class="col">
        <input class="form-control" placeholder="Digite um número" v-model="state.firstNum" @input="calc()" type="number">
      </div>
      <div class="col">
        <input class="form-control" placeholder="Digite um número" v-model="state.secondNum" @input="calc()" type="number">
      </div>
    </div>

    <select class="form-select" v-model="state.operationNum" @change="calc()">
      <option disabled value="1" >Escolha uma operação</option>
      <option value="soma" >Soma</option>
      <option value="sub">Subtração</option>
      <option value="multi">Multiplicação</option>
      <option value="divi">Divisão</option>
      <option value="poten">Potenciação</option>
      <option value="radi">Radiciação</option>
    </select>
    <div class="mt-3">
      <input disabled class="form-control" type="text" v-model="state.result" >
    </div>
  </form>
</template>
