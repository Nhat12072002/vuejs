<!-- src/components/DynamicTabbedLayout.vue -->
<template>
  <div class="dynamic-tabbed-layout">
    <div class="tabs">
      <button v-for="(tab, index) in tabs" :key="index" @click="switchComponent(tab.component)">
        {{ tab.label }}
      </button>
    </div>

    <keep-alive>
      <component :is="currentComponent" />
    </keep-alive>
  </div>
</template>

<script>
import ComponentA from './ComponentA.vue';
import ComponentB from './ComponentB.vue';
import ComponentC from './ComponentC.vue';

export default {
  data() {
    return {
      currentComponent: null,
      tabs: [
        { label: 'Tab 1', component: 'ComponentA' },
        { label: 'Tab 2', component: 'ComponentB' },
        { label: 'Tab 3', component: 'ComponentC' },
      ],
    };
  },
  methods: {
    switchComponent(component) {
      this.currentComponent = component;
    },
  },
  components: {
    ComponentA,
    ComponentB,
    ComponentC,
  },
};
</script>

<style scoped>
.dynamic-tabbed-layout {
  max-width: 600px;
  margin: 0 auto;
  padding: 20px;
  border: 1px solid #ddd;
  border-radius: 8px;
  box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
}

.tabs {
  display: flex;
  margin-bottom: 20px;
}

.tabs button {
  background-color: #3498db;
  color: white;
  border: none;
  padding: 10px 15px;
  border-radius: 4px;
  cursor: pointer;
}

.tabs button:hover {
  background-color: #2980b9;
}

</style>