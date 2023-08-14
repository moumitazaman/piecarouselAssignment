<script setup>
import { ref,onMounted,onBeforeUnmount,nextTick,onUnmounted } from 'vue'

const images =ref([
    'https://images.unsplash.com/photo-1636522637419-50322e27b0a5?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=387&q=80',
    'https://images.unsplash.com/photo-1691428051155-23baefc80bff?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHx0b3BpYy1mZWVkfDF8eGpQUjRobGtCR0F8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=500&q=60',
    'https://images.unsplash.com/photo-1690228244205-7617c71b1136?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=464&q=80',
    'https://images.unsplash.com/photo-1684378784787-1b8ca456118e?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=435&q=80'
])

let carousel = null

onMounted(()=>{
  carousel = new Flickity('#carousel',{})
})

onBeforeUnmount(() =>{
    
   
    carousel.destroy()
    //carousel =null

    
})


</script>

<template>
   
   <div class="mx-auto items" id="carousel">
    <div :style="`background-image:url(${image})`" class="item" v-for="image, index in images" :key="index">{{ index + 1 }}</div>
  </div>

</template>

<style scoped>
.items {
  width: 600px;
  height: 500px;
}

.item {
  width: 600px;
  height: 500px;
  background-color: #ccc;
  background-size: cover;
}
</style>
