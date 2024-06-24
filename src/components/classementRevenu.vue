<template>
  <div class="col-4">
    <table class="table">
      <thead>
      <tr>
        <th scope="col">&nbsp;</th>
        <th scope="col">jour</th>
        <th scope="col">gain</th>
      </tr>
      </thead>
      <tbody>
      <tr v-for="(valueTable, indexTable) in sortedTop5Revenues" :key="indexTable">
        <td>{{ indexTable + 1 }}</td>
        <td>{{ valueTable.date }}</td>
        <td>{{ valueTable.revenu_total }}</td>
      </tr>
      </tbody>
    </table>
  </div>
</template>

<script setup>
import jsonData from "/data.json";

let dataTable = jsonData;

let top5Revenues = dataTable.slice(0, 5);

let sortedTop5Revenues = top5Revenues.slice().sort((a, b) => b.revenu_total - a.revenu_total);
</script>

<style scoped>
/* Styles spécifiques au composant */
</style>
