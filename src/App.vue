<template>
  <HeatMap :options="chartOptions" :series="series" />
</template>

<script>
function generateData(count, yrange) {
  var i = 0;
  var series = [];
  while (i < count) {
    var x = (i + 1).toString();
    var y =
      Math.floor(Math.random() * (yrange.max - yrange.min + 1)) + yrange.min;
    series.push({
      x: '',
      y: y,
    });
    i++;
  }
  return series;
}
import HeatMap from './components/HeatMap.vue';
export default {
  components: {
    HeatMap,
  },
  data: function () {
    return {
      chartOptions: {
        chart: {
          id: 'chart',
          height: 'auto',
          width: '100%',
          type: 'heatmap',
          redrawOnParentResize: false,
          redrawOnWindowResize: false,
        },
        xaxis: {
          // categories: [1991, 1992, 1993, 1994, 1995, 1996, 1997, 1998],
        },
        dataLabels: {
          enabled: false,
        },
        plotOptions: {
          heatmap: {
            radius: 0,
            enableShades: false,
            colorScale: {
              ranges: [
                {
                  from: -Infinity,
                  to: 0,
                  color: 'rgba(27, 31, 35, 0.06)',
                },
                {
                  from: 1,
                  to: 5,
                  color: '#9be9a8',
                },
                {
                  from: 6,
                  to: 10,
                  color: '#40c463',
                },
                {
                  from: 11,
                  to: 30,
                  color: '#30a14e',
                },
                {
                  from: 31,
                  to: Infinity,
                  color: '#216e39',
                },
              ],
            },
          },
        },
        legend: {
          show: false,
        },
      },
      series: [
        {
          name: 'Mon',
          data: generateData(52, {
            min: 0,
            max: 90,
          }),
        },
        {
          name: '',
          data: generateData(52, {
            min: 0,
            max: 90,
          }),
        },
        {
          name: 'Wed',
          data: generateData(52, {
            min: 0,
            max: 90,
          }),
        },
        {
          name: '',
          data: generateData(52, {
            min: 0,
            max: 90,
          }),
        },
        {
          name: 'Fri',
          data: generateData(52, {
            min: 0,
            max: 90,
          }),
        },
        {
          name: '',
          data: generateData(52, {
            min: 0,
            max: 90,
          }),
        },
        {
          name: 'Sun',
          data: generateData(52, {
            min: 0,
            max: 90,
          }),
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
