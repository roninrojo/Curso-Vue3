<script setup>
  import { computed, ref } from 'vue';
  let message = ref('')
  const reverseText = computed(() =>  message.value.split('').reverse().join('') )

</script>
<template>
  <div>
    <h1>Computed Properties Composition API</h1>
    <input type="text" v-model="message">
    <h3>{{ reverseText }}</h3>  
  </div>
</template>
<style scoped>
  
</style>