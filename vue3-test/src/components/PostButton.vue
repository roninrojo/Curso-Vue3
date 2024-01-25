<template>
    <button class="post-btn" @click="$emit('addLike')">💚</button>
</template>

<script setup>
</script>

<style scoped>
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