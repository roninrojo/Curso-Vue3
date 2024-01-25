<template>
    <p>Vota este post: {{ counter }}</p>
    <div class="post-votes">
        <button class="post-votes__button" v-on:click="addCounter">+</button> 
        <button class="post-votes__button" v-on:click="subCounter">-</button> 
    </div>
</template>
<script>
import { defineComponent } from 'vue';
export default defineComponent({
    name: "CounterOptionAPI",
    data() {
        let counter = 0
        return {counter};
    },
    // components
    // props
    // etc
    methods: {
        addCounter() {
            this.counter++
        },
        subCounter() {
            if(this.counter > 0) this.counter--
        }
    },
})
</script>
<style>
    .post-votes {
        display: flex;
        width: 100%;
        gap:20px;
    }
    .post-votes__button {
        background-color: mediumaquamarine;
        color: #000;
        border: 0;
        border-radius: 3px;
        
    }
</style>