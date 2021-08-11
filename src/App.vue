<template>
  <HeatMap width="500" type="bar" :options="chartOptions" :series="series" />
</template>

<script>
import HeatMap from './components/HeatMap.vue';
export default {
  components: {
    HeatMap,
  },
  data: function () {
    return {
      chartOptions: {
        chart: {
          id: 'vuechart-example',
        },
        xaxis: {
          categories: [1991, 1992, 1993, 1994, 1995, 1996, 1997, 1998],
        },
      },
      series: [
        {
          name: 'series-1',
          data: [30, 40, 35, 50, 49, 60, 70, 91],
        },
      ],
    };
  },
};
</script>

<style>
* {
  border: 0;
  margin: 0;
  padding: 0;
  outline: none;
  list-style: outside none;
  box-sizing: border-box;
}
</style>
