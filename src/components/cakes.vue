<template>
  <div>
    <button type="button" @click="update">Add Beverage - child</button>
    <hr>
    <button v-on:click="deleteCakes">Delete an item</button>
    <ul>
      <li v-for="(cake, index) in cakes" :key="index" @click="cake.show = !cake.show">
        <p>{{ cake.name }}</p>
        <p v-show="cake.show">{{ cake.tastyness }}</p>
      </li>
    </ul>
  </div>
  
</template>

<script>
  export default {
    props: {
      cakes: {
        type: Array,
        required: true
      }
    },
    data() {
      return {
     
      }
    },
    methods: {
      deleteCakes: function () {
        this.cakes.pop() 
      },
      update: function () {
        this.$emit('update');
      }
    }
  }
</script>

<style scoped>
ul {
  display:flex;
  max-width: 1000px;
  margin: 20px auto;
  padding: 10px;
  box-sizing: border-box;
}
li {
  list-style: none;
  padding: 20px;
  margin: 10px;
  text-align: center;
  border: 1px solid #229966;
  flex-grow: 1;
  flex-basis: 200px;
}
</style>