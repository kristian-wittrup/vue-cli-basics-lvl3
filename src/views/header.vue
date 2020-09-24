<template>
  <header>
    <h3 @click="changeStuff">{{ title }}</h3>

  </header>
</template>

<script>
import { bus } from '../main.js'

  export default {
    data() {
      return {
        title: 'Webapp Title much awesome!'
      }
    },
    methods: {
      changeStuff: function () {
        bus.$emit('stuffChanged', 'I changed stuff with the event bus')
      }
    }
  }
</script>

<style scoped>
    header {
      background-color: darkgrey;
      padding: 10px;
      height: 50px;
      text-align: center;
      color:#ffffff;
    }
</style>