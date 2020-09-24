<template>
  <div>
    <h3>Sign Up One</h3>
    <input v-model="message" placeholder="edit me">
    <p>Message is: {{ message }}</p>
  </div>
</template>

<script>
  export default {
    data() {
      return {
        message: ''
      }
    }
  }
</script>

<style scoped>

</style>