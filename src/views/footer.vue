<template>
  <footer>
    <p>{{ footerText }}</p>
    <button type="button" @click="component = 'signupone'">Sign Up One</button>
    <button type="button" @click="component = 'signuptwo'">Sign Up Two</button>
    <keep-alive>
      <component v-bind:is="component"></component>
    </keep-alive>
  </footer>
</template>

<script>
import { bus } from '../main.js'
import signUpOne from '../components/signUpOne.vue'
import signUpTwo from '../components/signUpTwo.vue'

  export default {
    components: {
      'signupone': signUpOne,
      'signuptwo': signUpTwo,
    },


    data() {
      return {
        component: 'signupone',
        message: '',
        footerText: 'Copyright anno 2019'
      }
    },
    created() {
      bus.$on('stuffChanged', (data) => {
        this.footerText = data;
      })
    }
  }
</script>

<style scoped>
  footer {
    background-color: lightcyan;
    padding: 10px;
    text-align: center;
  }
</style>