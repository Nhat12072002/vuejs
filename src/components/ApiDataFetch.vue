<!-- src/components/ApiDataFetch.vue -->
<template>
  <div class="api-data-fetch">
    <h2>Data from API</h2>
    <button @click="fetchData">Fetch Data</button>
    <div v-if="loading" class="loading">Loading...</div>
    <ul v-else-if="data.length > 0" class="data-list">
      <li v-for="item in data" :key="item.id">{{ item.title }}</li>
    </ul>
    <p v-else>No data available. Click "Fetch Data" to load.</p>
  </div>
</template>

<script>
import axios from 'axios';

export default {
  data() {
    return {
      data: [],
      loading: false
    };
  },
  methods: {
    async fetchData() {
      this.loading = true;
      try {
        const response = await axios.get('https://jsonplaceholder.typicode.com/todos');
        this.data = response.data;
      } catch (error) {
        console.error('Error fetching data:', error);
      } finally {
        this.loading = false;
      }
    }
  }
};
</script>

<style scoped>
/* Component styles go here */
.api-data-fetch {
  text-align: center;
  padding: 20px;
}

button {
  background-color: #3498db;
  color: white;
  padding: 10px 20px;
  font-size: 16px;
  border: none;
  cursor: pointer;
  transition: background-color 0.3s ease;
}

button:hover {
  background-color: #2980b9;
}

.loading {
  margin-top: 20px;
  font-size: 18px;
}

.data-list {
  list-style: none;
  padding: 0;
  margin: 20px 0;
}

.data-list li {
  margin: 10px 0;
  padding: 10px;
  background-color: #f2f2f2;
  border-radius: 8px;
}

p {
  color: #777;
}
</style>