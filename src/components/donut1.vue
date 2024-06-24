<template>
  <div class="col-6">
    <canvas id="donut1"></canvas>
  </div>
</template>


<script setup>
import Chart from 'chart.js/auto';
import {onMounted} from "vue";
const initChart = () => {

  const ctx = document.querySelector('#donut1');
  const data = {
    labels: ['france', 'espagne', 'USA', 'japon', 'chine'],
    datasets: [
      {
        label: 'france',
        data: 47,
      },
      {
        label: 'espagne',
        data: 28,
      },
      {
        label: 'USA',
        data: 17,
      },
      {
        label: 'japon',
        data: 9,
      },
      {
        label: 'chine',
        data: 18,
      },
    ]}

  new Chart(ctx, {
    type: 'doughnut',
    data: data,
    options: {
      responsive: true,
      plugins: {
        legend: {
          position: 'top',
        },
        title: {
          display: true,
          text: 'Chart.js Doughnut Chart'
        }
      }
    },
  });
};

onMounted(() => {
  initChart();
});
</script>

<style scoped>

</style>

