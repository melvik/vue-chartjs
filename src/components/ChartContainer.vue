<template>
  <div class="container">
    <bar-chart :chartdata="chartdata" :options="options" />

    <radar-chart :chartdata="chartdata" :options="options" />
  </div>
</template>

<script>
import BarChart from "./chart.vue"
import RadarChart from "./rchart.vue"

export default {
  name: "LineChartContainer",
  components: {
    BarChart,
    RadarChart
  },
  data() {
    return {
      chartdata: {
        labels: ["January", "February", "March", "April", 'May', 'June', 'July'],
        datasets: [
          {
            label: "Months",
            borderColor: '#f87676',
            // backgroundColor: ["#f87676", "#abc001", "#b10678", "#676700"],
            data: [55, 22, 33, 44, 24, 27, 31],
            minBarLength: 0
          }
        ]
      },
      options: {
        responsive: false,
        maintainAspectRatio: false,
        scales: {
          yAxes: [
            {
              ticks: {
                beginAtZero: true
              }
            }
          ]
        }
      }
    }
  }
}
</script>