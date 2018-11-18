<template>
  <div id="charts">
    <canvas 
      id="planet-chart" 
      class="minicharts"/>
  </div>
</template>

<script>
import planetChartData from '@/store/chart-data.js'
export default {
  data() {
    return {
      planetChartData: planetChartData
    }
  },
  mounted() {
    this.createChart('planet-chart', this.planetChartData)
  }
}
</script>
