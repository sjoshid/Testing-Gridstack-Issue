<script setup lang="ts">
import {GridStack} from 'gridstack';
import {onMounted} from 'vue'

let grid: GridStack;

onMounted(() => {
    var options = {
      // put in gridstack options here
      disableOneColumnMode: true, // for jfiddle small window size
      float: false,
    };
    grid = GridStack.init(options);
});
</script>

<template>
    <p>Helllo</p>
  <div class="grid-stack">
    <div class="grid-stack-item">
      <div class="grid-stack-item-content">Item 1</div>
    </div>
    <div class="grid-stack-item" gs-w="2">
      <div class="grid-stack-item-content">Item 2 wider</div>
    </div>
  </div>
</template>

<style>
@import "gridstack/dist/gridstack.css";

.grid-stack {
  background: lightgoldenrodyellow;
}

.grid-stack-item-content {
  color: #2c3e50;
  text-align: center;
  background-color: #18bc9c;
}
</style>
