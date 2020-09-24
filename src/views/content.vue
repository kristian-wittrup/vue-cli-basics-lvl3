<template>
  <div>
    <ul>
      <li v-for="(beverage, index) in beverages" :key="index">
        {{ beverage.brands }}
      </li>
    </ul>
    <cakes v-bind:cakes="cakes" v-on:update="addBeverage" />
  </div>
</template>

<script>
import cakes from './../components/cakes.vue'
  export default {
      components: {
        'cakes': cakes
      },
      data () {
        return {
          beverages: [],
          cakes: [
            { name: 'Chocolatecake', tastyness: 'Super delisssh', show: false },
            { name: 'Bananacake', tastyness: 'Fresh and sweet', show: false },
            { name: 'Muffins', tastyness: 'Yummie!', show: false },
            { name: 'Donuts', tastyness: 'Mmmmhhhh Homer like!', show: false },
            { name: 'Healthy cake', tastyness: 'Get outta here!!', show: false },
            { name: 'Cinnamonbuns', tastyness: 'Ohhh yeah!!!', show: false },
          ],
        }
      },
      methods: {
        addBeverage() {
         this.beverages.push({ brands: "some beverage brand" })
        }
      }
    }
</script>

<style scoped>

</style>