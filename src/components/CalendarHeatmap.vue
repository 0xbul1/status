<template>
  <CalendarHeatmap :values="values" :end-date="endDate" />
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
};
</script>
