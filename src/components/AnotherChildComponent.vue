<!-- AnotherChildComponent.vue -->
<template>
    <div class="container">
      <h2>Component Con Khác</h2>
      <button @click="guiSuKienKhac">Gửi Sự Kiện Khác</button>
    </div>
  </template>
  
  <script>
  
  
  export default {
    methods: {
      guiSuKienKhac() {
        
        this.$emit('suKienKhac', 'Dữ liệu từ Component Con Khác');
      },
    },
  };
  </script>
  
  <style scoped>
  .container {
    background-color: #e74c3c;
    color: white;
    padding: 20px;
    border-radius: 8px;
    box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
    margin-top: 20px;
  }
  button {
    background-color: #c0392b;
    color: white;
    border: none;
    padding: 10px 15px;
    border-radius: 4px;
    cursor: pointer;
  }
  button:hover {
    background-color: #a93226;
  }
  </style>