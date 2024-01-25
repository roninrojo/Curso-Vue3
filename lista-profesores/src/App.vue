<script setup>
import AddTeacher from './components/AddTeacher.vue';
// import ListTeachers from './components/ListTeachers.vue';
</script>

<template>
  <h3>Introduce los datos de un profesor</h3>
  <div class="container">
    <AddTeacher />
  </div>
</template>

<style>
  html {
    font-family: system-ui, -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, 'Open Sans', 'Helvetica Neue', sans-serif;
  }
  .container {
    display: flex;
    gap: 1rem;
  }
</style>
