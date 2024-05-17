<template>
    <div class="child-component">
      <h2>Child Component</h2>
      <button @click="emitData" class="btn-send">Send Data to Parent</button>
      <slot :slotData="slotData"></slot>
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        slotData: 'This is data from child'
      };
    },
    methods: {
      emitData() {
        this.$emit('data-updated', this.slotData);
      }
    }
  };
  </script>
  
  <style scoped>
  .child-component {
    padding: 20px;
    border: 1px solid #ddd;
    border-radius: 10px;
    background-color: #ffffff;
    max-width: 400px;
    margin: 20px auto;
    box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
    transition: transform 0.3s, box-shadow 0.3s;
  }
  
  .child-component:hover {
    transform: translateY(-5px);
    box-shadow: 0 8px 16px rgba(0, 0, 0, 0.2);
  }
  
  .child-component h2 {
    font-size: 22px;
    color: #333;
    margin-bottom: 20px;
  }
  
  .btn-send {
    padding: 10px 20px;
    font-size: 16px;
    color: #fff;
    background-color: #007BFF;
    border: none;
    border-radius: 4px;
    cursor: pointer;
    transition: background-color 0.3s, transform 0.3s;
  }
  
  .btn-send:hover {
    background-color: #0056b3;
    transform: translateY(-2px);
  }
  
  .btn-send:active {
    background-color: #004494;
  }
  </style>
  