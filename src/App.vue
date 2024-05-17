<template>
  <div id="app">
    <ParentComponent />
  </div>
</template>

<script>
import ParentComponent from './components/ParentComponent.vue';

export default {
  components: {
    ParentComponent
  }
};
</script>

<style scoped>
#app {
  font-family: 'Helvetica Neue', Arial, sans-serif;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
  background-color: #86b0ef;
  min-height: 10vh;
  display: flex;
  align-items: center;
  justify-content: center;
}
</style>
