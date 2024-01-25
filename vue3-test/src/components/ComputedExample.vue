<script>
  import { defineComponent } from 'vue';
  export default defineComponent({
    name: "ComputedExample",
    data() {
      return {
          message:""
        }
    },
    computed: {
      reverseText() {
          return this.message.split('').reverse().join('')
        }
      }
    })

</script>
<template>
  <div>
    <input type="text" v-model="message">
    <h3>{{ message }}</h3>  
    <h3>{{ reverseText }}</h3>  
  </div>
</template>
<style scoped>
  
</style>