<script setup>
import { ref, computed } from 'vue';
let valor = ref('')
const calcIva = computed(() => {
  return (valor.value * 21) / 100
})

const total = computed(() => {
  return calcIva.value + Number(valor?.value)
})
</script>
<template>
  <div>
    <input type="text" v-model="valor">
    <p>IVA 21% ➡️ {{ calcIva }} €</p>
    <h3>Total: {{ total }} €</h3>
  </div>
</template>
<style scoped>
  p {margin: 1rem auto;}
  h3 {
    font-weight: bold;
  }
</style>