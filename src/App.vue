<script setup lang="ts">
import MaskedInput from '@/components/MaskedInput.vue'
import { ref } from 'vue'
const input_value = ref(0)
</script>

<template>
  <div>
    {{input_value}} <br/>
    {{typeof input_value}} <br/>
    <MaskedInput v-model="input_value" />
  </div>
</template>

<style scoped>
.logo {
  height: 6em;
  padding: 1.5em;
  will-change: filter;
}
.logo:hover {
  filter: drop-shadow(0 0 2em #646cffaa);
}
.logo.vue:hover {
  filter: drop-shadow(0 0 2em #42b883aa);
}
</style>
