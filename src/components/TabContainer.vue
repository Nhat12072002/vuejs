<!-- TabContainer.vue -->
<template>
    <div class="tab-container">
      <div class="header">
        <slot name="header"></slot>
      </div>
  
      <div class="tab-buttons">
        <button
          v-for="(tab, index) in tabs"
          :key="index"
          @click="changeTab(index)"
          :class="{ active: activeTabIndex === index }"
        >
          {{ tab }}
        </button>
      </div>
  
      <div class="tab-content">
        <transition name="fade" mode="out-in">
          <div :key="activeTabIndex">
            <slot :tabIndex="activeTabIndex"></slot>
          </div>
        </transition>
      </div>
  
      <div class="footer">
        <slot name="footer" :message="footerMessage"></slot>
      </div>
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        activeTabIndex: 0,
        tabs: ['Tab 1', 'Tab 2', 'Tab 3', 'Tab 4'],
        footerMessage: 'Hand-ons for Slot on Vue.js'
      };
    },
    methods: {
      changeTab(index) {
        this.activeTabIndex = index;
      }
    }
  };
  </script>
  
  <style scoped>
  .tab-container {
    max-width: 600px;
    margin: 0 auto;
    border: 1px solid #ddd;
    border-radius: 8px;
    overflow: hidden;
  }
  
  .header, .footer {
    background-color: #3498db;
    color: white;
    padding: 10px;
    text-align: center;
  }
  
  .tab-buttons {
    display: flex;
  }
  
  .tab-buttons button {
    flex: 1;
    padding: 10px;
    background-color: #3498db;
    color: rgb(0, 0, 0);
    border: none;
    cursor: pointer;
    transition: background-color 0.3s ease;
  }
  
  .tab-buttons button.active {
    background-color: #b92929;
  }
  
  .tab-buttons button:hover {
    background-color: #2980b9;
  }
  
  .tab-content {
    margin-top: 15px;
    border-top: 1px solid #000000;
    padding: 15px;
  }
  
  .footer {
    margin-top: 15px;
  }
  
  .fade-enter-active, .fade-leave-active {
    transition: opacity 0.5s;
  }
  .fade-enter, .fade-leave-to {
    opacity: 0;
  }
  </style>