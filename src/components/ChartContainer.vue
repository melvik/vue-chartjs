<template>
  <div class="container">
    <button @click="updateData()">update</button>
    <random-chart :chartdata="chartdata2" :options="options2"/>
  </div>
</template>

<script>
import RandomChart from "./RandomChart.vue"

export default {
  name: "LineChartContainer",
  components: {
    RandomChart
  },
  data() {
    return {
        chartdata2: {
            labels: ["January", "February", "March", "April", 'May', 'June', 'July'],
            datasets: [
            {
                label: "Months",
                borderColor: '#f87676',
                // backgroundColor: ["#f87676", "#abc001", "#b10678", "#676700"],
                data: [this.getRandomInt(), this.getRandomInt(), this.getRandomInt(), this.getRandomInt(), this.getRandomInt(), this.getRandomInt(), this.getRandomInt()],
                minBarLength: 0
            }
            ]
        },
        options2: {
            responsive: true,
            maintainAspectRatio: false
        }
    }
  },
  methods: {
    updateData () {
      this.chartdata2 = {
            labels: ["January", "February", "March", "April", 'May', 'June', 'July'],
            datasets: [
            {
                label: "Months",
                borderColor: '#f87676',
                // backgroundColor: ["#f87676", "#abc001", "#b10678", "#676700"],
                data: [this.getRandomInt(), this.getRandomInt(), this.getRandomInt(), this.getRandomInt(), this.getRandomInt(), this.getRandomInt(), this.getRandomInt()],
                minBarLength: 0
            }
            ]
        }
      // this.chartdata2.datasets[0].data = [this.getRandomInt(), this.getRandomInt(), this.getRandomInt(), this.getRandomInt(), this.getRandomInt(), this.getRandomInt(), this.getRandomInt()]
      // console.log(this.chartdata2)
    },
    getRandomInt () {
      return Math.floor(Math.random() * (50 - 5 + 1))
    }
  }
}
</script>