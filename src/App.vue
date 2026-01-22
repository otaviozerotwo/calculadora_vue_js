<script setup>

</script>

<template>
  <div class="container">
    <h1 class="text-center py-5">Calculadora Aritmética</h1>
    <div class="row justify-content-center">
      <div class="col-md-4 col-sm-6 col-lg-4">
        <div class="mb-3">
          <input type="number" class="w-100 rounded">
        </div>
        <div class="mb-3 d-flex justify-content-end">
          <select class="w-25 rounded">
            <option value="" class="symbol" disabled selected hidden>...</option>
            <option value="" class="symbol text-center">+</option>
            <option value="" class="symbol text-center">-</option>
            <option value="" class="symbol text-center">x</option>
            <option value="" class="symbol text-center">/</option>
          </select>
        </div>
        <div class="mb-3">
          <input type="number" class="w-100 rounded">
        </div>
        <div class="mb-3 d-flex justify-content-end">
          <span class="symbol">=</span>
        </div>
        <div class="mb-3">
          <input type="number" class="w-100 rounded">
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
  .symbol {
    font-size: 48px;
    font-weight: bold;
  }
</style>
