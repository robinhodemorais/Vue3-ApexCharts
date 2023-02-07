<template>
  <div class="container mx-auto box-border bg-orange-100">
    <HelloApexcharts robinhoChart="PAI" :pSeries="series" />
  </div>
</template>

<script setup>
// import HelloWorld from "./components/HelloWorld.vue";

import { ref, onMounted } from "vue";
import HelloApexcharts from "./components/HelloApexcharts.vue";

let series = ref([]);

series.value = [
  {
    name: "series-2",
    data: [200, 51, 65, 71, 89, 62, 69, 91, 148],
  },
];

onMounted(() => {
  console.log("PAI series.value", series.value);
});
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
