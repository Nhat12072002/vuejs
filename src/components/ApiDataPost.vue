<template>
  <div>
    <h2>Post Data to API</h2>
    <form @submit.prevent="submitPostData">
      <label for="title">Title:</label>
      <input type="text" v-model="formData.title" required />
      <button type="submit">Submit</button>
    </form>
  </div>
</template>

<script>
import axios from 'axios';

export default {
  data() {
    return {
      formData: {
        title: ''
      }
    };
  },
  methods: {
    async submitPostData() {
      try {
        const response = await axios.post('https://jsonplaceholder.typicode.com/todos', this.formData);
        console.log('Data posted successfully:', response.data);
        // You can handle the response or update the UI as needed
      } catch (error) {
        console.error('Error posting data:', error);
      }
    }
  }
};
</script>

<style scoped>
/* Component styles go here */
</style>
