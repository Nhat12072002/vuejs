<!-- App.vue -->
<template>
  <div id="app">
    <ParentComponent />
    <AnotherChildComponent />
  </div>
</template>

<script>
import ParentComponent from './components/ParentComponent.vue';
import AnotherChildComponent from './components/AnotherChildComponent.vue';
import { createApp } from 'vue';



export default {
  components: {
    ParentComponent,
    
  },
};
</script>

<style>
#app {
  font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
  text-align: center;
  color: #2c3e50;
  margin-top: 20px;
}
</style>