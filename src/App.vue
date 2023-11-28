<template>
  <div id="app">
    <ApiDataFetch />
    <ApiDataPost />
  </div>
</template>

<script>
import ApiDataFetch from './components/ApiDataFetch.vue';
import ApiDataPost from './components/ApiDataPost.vue';

export default {
  name: 'App',
  components: {
    ApiDataFetch,
    ApiDataPost
  }
};
</script>

<style>
#app {
  font-family: 'Arial', sans-serif;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
