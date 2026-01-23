<script setup>
  import { reactive } from 'vue';

  const state = reactive({
    vlr_input_1: 0,
    vlr_input_2: 0,
    operation: '',
  });

  const getInput1 = (e) => {
    return state.vlr_input_1 = e.target.value;
  }

  const getInput2 = (e) => {
    return state.vlr_input_2 = e.target.value;
  }

  const getOperation = (e) => {
    state.operation = e.target.value;

    switch (state.operation) {
      case '+':
        return sumOperation();
      case '-':
        return minusOperation();
      case '*':
        return multiplyOperation();
      case '/':
        return divisionOperation();
      default:
        return 'ERROR';
    }
  }

</script>

<template>
  <div class="container">
    <h1 class="text-center py-5">Calculadora Aritmética</h1>
    <div class="row justify-content-center">
      <div class="col-md-4 col-sm-6 col-lg-4">
        <div class="mb-3 d-flex justify-content-end">
          <input type="number" class="input w-100 border-top-0 border-start-0 border-end-0 text-end fs-1" @keyup="getInput1">
        </div>
        <div class="mb-3 d-flex justify-content-end">
          <div class="d-flex justify-content-between align-items-center w-100 gap-2">
            <label class="select-label">Escolha a operação:</label>
            <select @change="getOperation" class="select w-25 symbol text-center border-top-0 border-start-0 border-end-0">
              <option value="" class="symbol" disabled selected hidden>...</option>
              <option value="+" class="symbol text-center">+</option>
              <option value="-" class="symbol text-center">-</option>
              <option value="*" class="symbol text-center">x</option>
              <option value="/" class="symbol text-center">/</option>
            </select>
          </div>
        </div>
        <div class="mb-3 d-flex justify-content-end">
          <input type="number" class="input w-100 border-top-0 border-start-0 border-end-0 text-end fs-1" @keyup="getInput2">
        </div>
        <div class="mb-3 d-flex justify-content-end">
          <span class="symbol">=</span>
        </div>
        <div class="mb-3 d-flex justify-content-end">
          <span class="result">0</span>
          {{ state.vlr_input_1 }}
          {{ state.operation }}
          {{ state.vlr_input_2 }}
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
  .select-label {
    font-size: 24px;
    margin: 0;
  }

  .select:focus,
  .input:focus {
    outline: none;
  }

  .input::-webkit-outer-spin-button,
  .input::-webkit-inner-spin-button {
    -webkit-appearance: none;
  }

  .symbol {
    font-size: 36px;
    font-weight: bold;
  }

  .result {
    font-size: 56px;
    font-weight: 500;
  }
</style>
