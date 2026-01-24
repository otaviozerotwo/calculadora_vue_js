<script setup>
  import { computed } from 'vue'

  const props = defineProps({
    input1: {
      type: [Number],
    },
    input2: {
      type: [Number],
    },
    operator: {
      type: String,
    },
    calculate: {
      type: Function,
    },
  })

  const result = computed(() => props.calculate(props.input1, props.input2, props.operator))
</script>

<template>
  <div class="mb-3 d-flex justify-content-end">
    <span class="result">{{ result }}</span>
  </div>
</template>

<style scoped>
  .result {
    font-size: 56px;
    font-weight: 500;
    word-break: break-all;
  }
</style>