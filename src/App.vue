<script setup>
  import { reactive } from 'vue';
  import Header from './components/Header.vue';
  import Input from './components/Input.vue';
  import Select from './components/Select.vue';
  import ShowResult from './components/ShowResult.vue';

  const state = reactive({
    vlr_input_1: 0,
    vlr_input_2: 0,
    operator: '',
    result: 0,
  });

  const getInput1 = (e) => {
    return state.vlr_input_1 = e.target.value;
  }

  const getInput2 = (e) => {
    return state.vlr_input_2 = e.target.value;
  }

  const calculate = (num1, num2, operator) => {
    switch (operator) {
      case '+':
        return Number(num1) + Number(num2);
      case '-':
        return Number(num1) - Number(num2);
      case '*':
        return Number(num1) * Number(num2);
      case '/':
        return Number(num1) / Number(num2);
      case '':
        return 0;
      default:
        return 'ERROR';
    }
  }
</script>

<template>
  <div class="main">
    <div class="container">
      <Header />
      <div class="row justify-content-center">
        <div class="col-md-4 col-sm-6 col-lg-4">
          <Input :getInput="getInput1" />
          <Select v-model:operator="state.operator" />
          <Input :getInput="getInput2" />
          <div class="mb-3 d-flex justify-content-end">
            <span class="symbol">=</span>
          </div>
          <ShowResult 
            :input1="state.vlr_input_1" 
            :input2="state.vlr_input_2" 
            :operator="state.operator" 
            :calculate="calculate" 
          />
        </div>
      </div>
    </div>
  </div>
</template>

<style>
  .main {
    height: 100vh;
    background-color: #D8C99B;
    color: #22223B;
  }
  .symbol {
    font-size: 36px;
    font-weight: bold;
    color: #22223B;
  }
</style>
