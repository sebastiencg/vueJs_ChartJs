<template>
  <div class="col-6">
    <canvas id="graphe1"></canvas>

  </div>
</template>


<script setup>
import Chart from 'chart.js/auto';
import {onMounted} from "vue";
import jsonData from '/data.json';

const initChart = () => {
  let chambres_occupees=[]
  let date=[]
  let revenu_total = []
  jsonData.forEach((element) =>{
    chambres_occupees.push(element.chambres_occupees)
    date.push(element.date)
    revenu_total.push(element.revenu_total)
  } );

  console.log(date)

  const ctx = document.querySelector('#graphe1');
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

