<script setup lang="ts">
import { GridStack } from 'gridstack'
import { onMounted } from 'vue'
import { Chart } from 'highcharts-vue'

let grid: GridStack

onMounted(() => {
  var options = {
    // put in gridstack options here
    disableOneColumnMode: true, // for jfiddle small window size
    float: false
  }
  grid = GridStack.init(options)
})

const wids = [
  {
    origin: [0, 0],
    dims: [3, 3],
    name: 'Router Saturation',
    chartOptions: {
      chart: {
        reflow: true
      },
      title: {
        text: 'Router Saturation 1'
      },
      series: [
        {
          data: [10, 20, 30]
        }
      ]
    }
  },
  {
    origin: [0, 3],
    dims: [3, 3],
    name: 'Router Saturation',
    chartOptions: {
      chart: {
        reflow: true
      },
      title: {
        text: 'Router Saturation 2'
      },
      series: [
        {
          data: [10, 20, 30]
        }
      ]
    }
  }
]
</script>

<template>
  <div class="grid-stack">
    <div
      v-for="(widget, index) in wids"
      :key="index"
      :gs-h="widget.dims[1]"
      :gs-w="widget.dims[0]"
      :gs-x="widget.origin[0]"
      :gs-y="widget.origin[1]"
      class="grid-stack-item"
    >
      <div class="grid-stack-item-content"><Chart :options="widget.chartOptions" /></div>
    </div>
  </div>
</template>

<style>
@import 'gridstack/dist/gridstack.css';

.grid-stack {
  background: lightgoldenrodyellow;
}

.grid-stack-item-content {
  color: #2c3e50;
  text-align: center;
  background-color: #18bc9c;
}
</style>
