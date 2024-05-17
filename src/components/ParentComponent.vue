<template>
    <div class="parent-component">
      <h1>Parent Component</h1>
      <ChildComponent @data-updated="updateDataFromChild">
        <template v-slot:default="slotProps">
          <p class="slot-data">Data from slot: {{ slotProps.slotData }}</p>
        </template>
      </ChildComponent>
      <p class="data-from-child">Data from child: {{ dataFromChild }}</p>
    </div>
  </template>
  
  <script>
  import ChildComponent from './ChildComponent.vue';
  
  export default {
    components: {
      ChildComponent
    },
    data() {
      return {
        dataFromChild: ''
      };
    },
    methods: {
      updateDataFromChild(data) {
        this.dataFromChild = data;
      }
    }
  };
  </script>
  
  <style scoped>
  .parent-component {
    padding: 30px;
    border: 1px solid #ddd;
    border-radius: 10px;
    background-color: #c29df0;
    max-width: 600px;
    margin: 20px;
    box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
    transition: transform 0.3s, box-shadow 0.3s;
  }
  
  .parent-component:hover {
    transform: translateY(-5px);
    box-shadow: 0 8px 16px rgba(0, 0, 0, 0.2);
  }
  
  .parent-component h1 {
    font-size: 24px;
    color: #333;
    margin-bottom: 20px;
  }
  
  .slot-data {
    font-size: 18px;
    color: #555;
    background-color: #eef;
    padding: 10px;
    border-radius: 5px;
  }
  
  .data-from-child {
    font-size: 18px;
    color: #ffffff;
    margin-top: 20px;
    font-weight: bold;
  }
  </style>
  