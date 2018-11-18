<template>
  <section class="container">
    <div id="App">
      <div id="content">
        <canvas ref="chart" />
      </div>
      <div id="charts">
        <canvas 
          id="planet-chart" 
          class="minicharts" />
      </div>
    </div>
  </section>
</template>

<script>
import Chart from 'chart.js'

export default {
  name: 'App',
  mounted() {
    var chart = this.$refs.chart
    var ctx = chart.getContext('2d')
    var myChart = new Chart(ctx, {
      type: 'bar',
      data: {
        labels: ['June', 'July', 'August', 'September', 'October', 'November'],
        datasets: [
          {
            label: 'Cash for Month',
            data: [12, 19, 3, 5, 2, 3],
            backgroundColor: [
              'rgba(255, 99, 132, 0.2)',
              'rgba(54, 162, 235, 0.2)',
              'rgba(255, 206, 86, 0.2)',
              'rgba(75, 192, 192, 0.2)',
              'rgba(153, 102, 255, 0.2)',
              'rgba(255, 159, 64, 0.2)'
            ],
            borderColor: [
              'rgba(255,99,132,1)',
              'rgba(54, 162, 235, 1)',
              'rgba(255, 206, 86, 1)',
              'rgba(75, 192, 192, 1)',
              'rgba(153, 102, 255, 1)',
              'rgba(255, 159, 64, 1)'
            ],
            borderWidth: 1
          }
        ]
      },
      options: {
        scales: {
          yAxes: [
            {
              ticks: {
                beginAtZero: true
              }
            }
          ]
        },
        onClick: event => {
          var activePoints = myChart.getElementsAtEventForMode(
            event,
            'point',
            myChart.options
          )
          if (activePoints.length > 0) {
            var firstPoint = activePoints[0]
            var label = myChart.data.labels[firstPoint._index]
            var value =
              myChart.data.datasets[firstPoint._datasetIndex].data[
                firstPoint._index
              ]
            alert(label + ': ' + value)
          }
        }
      }
    })
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
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
#content {
  margin: auto;
  width: 1024px;
  background-color: #ffffff;
  padding: 20px;
}
</style>
