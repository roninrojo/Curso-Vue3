<template>
    <!-- Bindeo de estilos -->
    <div class="post-card" :style="{ backgroundColor: bgc, color: tc }">
        <h3>{{ props?.title }}</h3>
        <p>{{ props?.content }}</p>
        <!-- Uso de componentes dentro de componentes -->
        <CounterCompositionAPI />
        <!-- Eventos -->
        <button class="post-btn" @click="handleBgColor">Leido</button>
        <!-- Uso de eventos desde hijo al padre con emit -->
        <p><PostButton v-on:add-like="hanleLike"/><span>{{ numLikes }}</span></p>
    </div>
</template>
<script setup>
// Usando composition API
import PostButton from './PostButton.vue';
import CounterCompositionAPI from './CounterCompositionAPI.vue';
// Referencia para pasar valores reactivos
import { ref } from 'vue';

let props = defineProps({
    title: String,
    content: String
})
let bgc = ref("#373737")
let tc = ref("#ebebeba3")

const handleBgColor = () => {
    bgc.value = "#ADD2C2"
    tc.value = "#000"
}

let numLikes = ref(0)

const hanleLike = () => {
    numLikes.value ++
}
    
</script>
<style scoped>
    .post-card {
        display: flex;
        flex-wrap: wrap;
        padding: 20px;
        border: 1px solid #000;
        border-radius: 10px;
        gap: 10px;
    }
    .post-btn {
    background-color: aquamarine;
    color: #000;
    cursor: pointer;
    padding: 10px;
    border:0;
    border-radius: 10px;


    &:hover {
        background-color: aqua;
    }
}
</style>