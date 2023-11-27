<!-- ChildComponent.vue -->
<template>
    <div class="container">
      <h2>Component Con</h2>
      <p>Thông điệp từ cha: {{ thongDiep }}</p>
      <button @click="guiSuKien">Gửi Sự Kiện</button>
    </div>
  </template>
  
  <script>
  export default {
    props: {
      thongDiep: String,
    },
    methods: {
      guiSuKien() {
        this.$emit('guiSuKien', 'Dữ liệu từ Component Con');
      },
    },
  };
  </script>
  
  <style scoped>
  .container {
    background-color: #3498db;
    color: white;
    padding: 20px;
    border-radius: 8px;
    box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
    margin-top: 20px;
  }
  button {
    background-color: #2ecc71;
    color: white;
    border: none;
    padding: 10px 15px;
    border-radius: 4px;
    cursor: pointer;
  }
  button:hover {
    background-color: #27ae60;
  }
  </style>