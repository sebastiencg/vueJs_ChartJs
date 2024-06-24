<template>
  <div class="col-6">
    <canvas id="graphe2"></canvas>

  </div>
</template>


<script setup>
import Chart from 'chart.js/auto';
import {onMounted} from "vue";
import jsonData from '/data.json';
import jsonData2 from '/data2.json';

const initChart = () => {
  let chambres_occupees=[]
  let id=[]
  let chambres_occupees2=[]

  let nombre_clients=[]
  jsonData.forEach((element) =>{
    chambres_occupees.push(element.chambres_occupees)
    id.push(element.id)
  } );
  jsonData2.forEach((element) =>{
    chambres_occupees2.push(element.chambres_occupees)
  } );


  const ctx = document.querySelector('#graphe2');
  new Chart(ctx, {
    type: 'line',
    data: {
      labels: id,
      datasets: [
        {
          label: 'nombre de chambres occupées cette annnee',
          data: chambres_occupees,
          borderWidth: 1
        },
        {
          label: 'nombre de chambres occupées annee derniere',
          data: chambres_occupees2,
          borderWidth: 1,
        },]
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

