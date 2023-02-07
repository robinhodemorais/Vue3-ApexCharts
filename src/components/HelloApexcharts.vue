<script setup>
import { defineProps, onMounted } from "vue";

const props = defineProps({
  robinhoChart: {
    type: String,
  },
  pSeries: {
    type: [String],
  },
});

const message = "A test message";
const chartOptions1 = {
  chart: {
    id: "taburan-hujan1",
    //width: "500px",
    height: "800px",
    zoom: { enabled: false },
  },
  xaxis: {
    categories: [1991, 1992, 1993, 1994, 1995, 1996, 1997, 1998, 1999],
  },
};
const chartOptions2 = {
  chart: {
    id: "taburan-hujan2",
    // width: "500px",
    height: "350",
    zoom: { enabled: false },
  },
  xaxis: {
    categories: ["Jan", "Feb", "Mar", "Apr", "May", "Jun", "Jul", "Aug", "Sep"],
  },
};

const chartSeries = [
  {
    name: "series-1",
    data: [10, 41, 35, 51, 49, 62, 69, 91, 148],
  },
];

onMounted(() => {
  console.log("filho props.pSeries", props.pSeries);
});
</script>
<template>
  <h1 class="text-cyan-700 text-xl font-black mb-5">
    {{ message }} - minha props {{ props.robinhoChart }}

    {{ props.pSeries }}
  </h1>
  <div class="bg-slate-100 lg:flex justify-between mx-5">
    <apexchart
      class="flex-1"
      height="300"
      type="bar"
      :options="chartOptions1"
      :series="props.pSeries"
    />
    <apexchart
      class="flex-1"
      height="300"
      type="line"
      :options="chartOptions2"
      :series="chartSeries"
    />
  </div>
</template>