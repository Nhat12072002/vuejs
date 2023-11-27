<!-- App.vue -->
<template>
  <div id="app">
    <TabContainer>
      <!-- Named Slot: Header -->
      <template v-slot:header>
        <h1>Tab Example</h1>
      </template>

      <!-- Compilation Scope (Single Slot): -->
      <template v-slot="{ tabIndex }">
        <div v-if="tabIndex === 0">
          <p>Content for Tab 1</p>
        </div>
        <div v-else-if="tabIndex === 1">
          <p>Content for Tab 2</p>
        </div>
        <div v-else-if="tabIndex === 2">
          <p>Content for Tab 3</p>
        </div>
        <div v-else-if="tabIndex === 3">
          <p>Content for Tab 4</p>
        </div>
      </template>

      <!-- Named Slot: Footer (Scoped Slot) -->
      <template v-slot:footer="{ message }">
        <p>{{ message }}</p>
      </template>
    </TabContainer>
  </div>
</template>

<script>
import TabContainer from './components/TabContainer.vue';

export default {
  name: 'App',
  components: {
    TabContainer
  }
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  text-align: center;
  color: #020202;
  margin-top: 60px;
}

/* Add your global styles here */
</style>