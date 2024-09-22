<template>
    <div>
      <button @click="toggleShow">{{ isShow ? 'Ẩn' : 'Hiện' }}</button>
    </div>
  </template>
  
  <script setup>
  import { ref } from 'vue';
  
  const isShow = ref(false);
  
  const toggleShow = () => {
    isShow.value = !isShow.value;
  };
  </script>
  
  <style scoped>
  button {
    padding: 10px;
    font-size: 16px;
    cursor: pointer;
  }
  </style>
  