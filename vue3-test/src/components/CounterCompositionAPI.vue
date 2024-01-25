<template>
    <p>Vota este post: {{ counter }}</p>
    <div class="post-votes">
        <button class="post-votes__button" @:click="addCounter">+</button> 
        <button class="post-votes__button" @:click="subCounter">-</button> 
    </div>
</template>
<script setup>
    import { ref } from 'vue';
    let counter = ref(0)
    const addCounter = () => counter.value++
    const subCounter = () => { if(counter.value > 0) counter.value--; }
</script>
<style>
    .post-votes {
        display: flex;
        width: 100%;
        gap:20px;
    }
    .post-votes__button {
        background-color: tomato;
        color: #000;
        border: 0;
        border-radius: 3px;
        
    }
</style>