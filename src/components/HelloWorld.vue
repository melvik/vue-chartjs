<template>
  <div>
      <LineChartContainer />
  </div>
</template>

<script>
import LineChartContainer from '@/components/ChartContainer'

export default {
  name: 'HelloWorld',
  props: {
    msg: String
  },
  components: {
    LineChartContainer
  }
}
</script>
