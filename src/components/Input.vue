<script setup>
  const props = defineProps(['getInput']);
</script>

<template>
  <div class="mb-3 d-flex justify-content-end">
    <input type="number" class="input w-100 border-top-0 border-start-0 border-end-0 text-end fs-1" @keyup="props.getInput">
  </div>
</template>

<style scoped>
  .input {
    background-color: #9A8C98;
  }

  .input:focus {
    outline: none;
  }

  .input::-webkit-outer-spin-button,
  .input::-webkit-inner-spin-button {
    -webkit-appearance: none;
  }
</style>