<script setup>
import { ref, onMounted,onBeforeUnmount } from 'vue';


let chart = null

const dataset = [
  300, 50, 100
]

const data = {
  labels: [
    'Red',
    'Blue',
    'Yellow'
  ],
  datasets: [{
    label: 'My Dataset',
    data: dataset,
    backgroundColor: [
      'rgb(255, 99, 132)',
      'rgb(54, 162, 235)',
      'rgb(255, 205, 86)',
      
    ],
    hoverOffset: 4
  }]
};

const config = {
  type: 'pie',
  data: data,
};

onMounted(() => {
  const ctx = document.getElementById('chart')
  chart = new Chart(ctx, config)
})

onBeforeUnmount(() => {
   
   chart.destroy()
   //chart=null;

})


</script>

<template>
  <div class=" mx-auto" style="height: 400px; width:400px;background-color: bisque;">
    <canvas id="chart">
    </canvas>
  </div>

 
</template>

<style scoped></style>