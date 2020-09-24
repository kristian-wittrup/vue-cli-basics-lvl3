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
          products: [
            { name: 'BMW', description:'Built Machine Wild!', price: '500.000', imgLink:'https://via.placeholder.com/300', specialOffer: false },
            { name: 'Merc', description:'It is a car!', price: '550.000', imgLink:'https://via.placeholder.com/300', specialOffer: false },
            { name: 'Aston Martin ', description:'Much pretty and Bondish', price: '600.000', imgLink:'https://via.placeholder.com/300', specialOffer: false },
            { name: 'Jaguar', description:'Also Bondish, and old school classic', price: '650.000', imgLink:'https://via.placeholder.com/300', specialOffer: false }
          ],
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