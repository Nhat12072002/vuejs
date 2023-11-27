<!-- src/App.vue -->
<template>
  <div id="app">
    <DynamicTabbedLayout />
  </div>
</template>

<script>
import DynamicTabbedLayout from './components/DynamicTabbedLayout.vue';

export default {
  components: {
    DynamicTabbedLayout,
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>