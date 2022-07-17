<script setup lang="ts">
import { ref, computed } from 'vue'
const props = defineProps({
  modelValue: Number,
})
function formatNumber(number: number) : string {
  return new Intl.NumberFormat('ru-RU').format(number)
}
const inputEl = ref<null | HTMLInputElement>(null)
const value = computed({
  get: () => formatNumber(props.modelValue),
  set(v) {
    const number = Number(v.replace(/\D/g, '')) || 0 // Может быть NaN
    // Применяем маску даже если number не поменялось
    inputEl ? inputEl.value.value = formatNumber(number) : false
    if (number !== props.modelValue) {
      emit('update:modelValue', number)
    }
  }
})
const emit = defineEmits(['update:modelValue'])
</script>

<template>
  <input v-model="value" ref="inputEl" />
</template>

<style scoped>
.read-the-docs {
  color: #888;
}
</style>
