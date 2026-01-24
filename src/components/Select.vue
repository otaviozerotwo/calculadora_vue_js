<script setup>
  const props = defineProps(['operator']);
  const emit = defineEmits(['update:operator']);
</script>

<template>
  <div class="mb-3 d-flex justify-content-end">
    <div class="d-flex justify-content-between align-items-center w-100 gap-2">
      <label class="select-label">Escolha a operação:</label>
      <select :value="props.operator" @change="$emit('update:operator', $event.target.value)" class="select w-25 symbol text-center border-top-0 border-start-0 border-end-0">
        <option value="" class="symbol" disabled selected hidden>...</option>
        <option value="+" class="symbol text-center">+</option>
        <option value="-" class="symbol text-center">-</option>
        <option value="*" class="symbol text-center">x</option>
        <option value="/" class="symbol text-center">/</option>
      </select>
    </div>
  </div>
</template>

<style scoped>
  .select-label {
    font-size: 24px;
    margin: 0;
  }

  .select:focus {
    outline: none;
  }
</style>