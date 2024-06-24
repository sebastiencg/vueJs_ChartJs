<script setup>
import 'bootstrap/dist/css/bootstrap.min.css';
import mapComponents from "./components/mapComponents.vue"
import graphe1 from "./components/graphe1.vue"
import graphe2 from "./components/graphe2.vue"
import graphe2ss from "./components/graphe2sd;uhg.vue"
import classementRevenu from "./components/classementRevenu.vue"
import donut1 from "./components/donut1.vue"


</script>

<template>
  <div class="container-fluid">
    <div class=" row">
      <graphe2ss/>
      <mapComponents/>
      <classement-revenu/>
      <graphe1/>
      <graphe2/>
      <donut1/>
    </div>

  </div>
</template>

<style scoped>

</style>
