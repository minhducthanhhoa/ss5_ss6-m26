<template>
    <div>
      <button @click="showMessage">Hiển thị</button>
  
      <button @click="hideMessage">Ẩn</button>
  
      <div v-show="isVisible" class="message-box">
        welcome to Rikkei Education 
      </div>
    </div>
  </template>
  
  <script setup>
  import { ref } from 'vue';
  
  const isVisible = ref(false);
  
  const showMessage = () => {
    isVisible.value = true;
  };

  const hideMessage = () => {
    isVisible.value = false;
  };
  </script>
  
  <style scoped>
  .message-box {
    margin-top: 20px;
    padding: 10px;
    background-color: #f0f0f0;
    border: 1px solid #ccc;
    font-size: 16px;
  }
  button {
    margin-right: 10px;
    padding: 10px;
    font-size: 16px;
    cursor: pointer;
  }
  </style>
  