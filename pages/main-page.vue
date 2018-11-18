<template>
  <section class="container">
    <div id="charts">
      <canvas 
        id="planet-chart" 
        class="minicharts" />
      <canvas 
        id="planet-chart2" 
        class="minicharts" />
    </div>
    <div class="minicards">
      <Card />
      <Card />
    </div>
  </section>
</template>

<script>
import Chart from 'chart.js'
import planetChartData from '@/store/chart-data.js'
import Card from '@/components/Card'

export default {
  layout: 'AppLayout',
  components: {
    Card
  },
  data() {
    return {
      planetChartData: planetChartData
    }
  },
  mounted() {
    this.createChart('planet-chart', this.planetChartData)
    this.createChart('planet-chart2', this.planetChartData)
  },
  methods: {
    createChart(chartId, chartData) {
      const ctx = document.getElementById(chartId)
      const myChart = new Chart(ctx, {
        type: chartData.type,
        data: chartData.data,
        options: chartData.options
      })
    }
  }
}
</script>

<style>
.container {
  display: grid;
}

#charts {
  display: flex;
}

.minicharts {
  max-width: 30%;
}
</style>
