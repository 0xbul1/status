<template>
  <CalendarHeatmap
    :values="values"
    :end-date="endDate"
    :range-color="['#ebedf0', '#9be9a8', '#40c463', '#30a14e', '#216e39']"
    :max="Infinity"
    :min="-Infinity"
    no-data-text=""
    tooltip-unit="stars"
  />
</template>
<script>
import { CalendarHeatmap } from 'vue3-calendar-heatmap';
export default {
  components: {
    CalendarHeatmap,
  },
  props: {
    values: {
      default: {},
    },
    endDate: {
      default: +new Date(),
    },
  },
  methods: {
    test(a, b, c) {
      console.log(a);
      console.log(b);
      console.log(c);
    },
  },
};
</script>
