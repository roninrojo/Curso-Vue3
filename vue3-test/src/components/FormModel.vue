<template>
  <!-- // v-model en input -->
  <input v-model="textRef" type="text">
  <p>Search: <strong>{{ textRef }}</strong></p>

  <!-- // v-model en checkbox -->
  <p><input type="checkbox" v-model="optionRef" > <span v-show="optionRef">Tienes marcada la opcion</span></p>

  <!--  v-model en select -->
  <select name="select" v-model="selectOptRef">
    <option value="1">Juegos de mesa</option>
    <option value="2">JavaScript</option>
    <option value="3">Diseño</option>
  </select>

  <h3>Categoría de los post {{ selectOptRef  }}</h3>


</template>
<script setup>
import { ref } from 'vue';
let textRef = ref('')
let optionRef = ref(false) 
let selectOptRef = ref(1)
  
</script>
<style>
</style>