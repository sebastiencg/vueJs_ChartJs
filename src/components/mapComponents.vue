<template>
  <div class="col-4">
    <canvas id="map"></canvas>

  </div>
</template>


<script setup>
import Chart from 'chart.js/auto';
import {onMounted} from "vue";
import jsonData from '/data.json';
const initChart = () => {
  let chambres_occupees=[]
  let client=[]
  let date=[]
  let revenu_total = []
  jsonData.forEach((element) =>{
    chambres_occupees.push(element.chambres_occupees)
    client.push(element.chambres_occupees)
    date.push(element.date)
    revenu_total.push(element.revenu_total)
  } );

  console.log(date)

  const ctx = document.querySelector('#map');
  new Chart(ctx, {
    type: 'line',
    data: {
      labels: date,
      datasets: [
        {
          label: 'nombre de chambres occupées',
          data: chambres_occupees,
          borderWidth: 1
        }]
    },
    options: {
      responsive: true,
      scales: {
        y: {
          beginAtZero: true
        }
      }
    }
  });
};

onMounted(() => {
  initChart();
});
</script>

<style scoped>

</style>

