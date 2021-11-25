<template>
  <div class="bar">
    <div>
      <canvas id="myChart"></canvas>
    </div>
  </div>
</template>

<style></style>

<script>
import { Bar } from "vue-chartjs";

export default {
  extends: Bar,
  mounted() {
    this.renderChart(data, options);
  },
};
</script>
