<template>
    <div>
      <h1>Thêm số ngẫu nhiên vào mảng</h1>
      <button @click="addRandomNumber">Random number</button>
  
      <h2>Mảng số hiện tại:</h2>
      <ul>
        <li v-for="(number, index) in numbers" :key="index">{{ number }}</li>
      </ul>
    </div>
  </template>
  
  <script setup>
  import { ref } from 'vue';
  
  const numbers = ref([]);
  
  const addRandomNumber = () => {
    const randomNumber = Math.floor(Math.random() * 100); 
    numbers.value.push(randomNumber); 
  };
  </script>
  
  <style scoped>
  button {
    margin-top: 10px;
    padding: 10px;
    font-size: 16px;
    cursor: pointer;
  }
  
  ul {
    list-style-type: none;
    padding: 0;
  }
  
  li {
    font-size: 18px;
    margin: 5px 0;
  }
  </style>
  