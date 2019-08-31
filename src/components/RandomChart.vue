<template>
  <div style="max-width: 400px;">
    <button @click="fillData()">Randomize</button>
    <radar-chart :chart-data="chartdata" :options="options"></radar-chart>
    <hr/>
    <b>data:</b>  {{chartdata1}}
    <hr/>
    <b>prop:</b>  {{chartdata}}
  </div>
</template>

<script>
  import RadarChart from './RadarChart.js'

  export default {
  props: {
      chartdata: {
        type: Object,
        default: null
      },
      options: {
        type: Object,
        default: null
      }
    },
    components: {
      RadarChart
    },
    data () {
      return {
        datacollection: null,
        chartdata1: {
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
        options1: {
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
    },
    mounted () {
      this.fillData()
    },
    methods: {
      fillData () {
        this.chartdata1 = {
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
      },
      getRandomInt () {
        return Math.floor(Math.random() * (50 - 5 + 1))
      }
    }
  }
</script>