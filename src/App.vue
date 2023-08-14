<script setup>
import { ref } from 'vue';
import Piechart from './components/Piechart.vue'
import Carousel from './components/Carousel.vue'

let isPie=ref(false)
let isCarousel=ref(false)

</script>

<template>
  <div v-show="isPie==true">
<Piechart/>
  </div>
  <div v-show="isCarousel==true">
<Carousel/>
</div>
 <div style="margin-top:25px">
 <button @click="isCarousel = false,
                isPie = true"  class="bg-orange-600 hover:bg-orange-700 text-white font-bold py-2 px-4 rounded focus:outline-none focus:shadow-outline" type="button">
           PieChart
            </button>
            --------------
            <button @click="isCarousel = true,
                isPie = false"  class="bg-orange-600 hover:bg-orange-700 text-white font-bold py-2 px-4 rounded focus:outline-none focus:shadow-outline" type="button">
          Carousel
            </button>
            </div>
  
</template>

<style scoped>
</style>
