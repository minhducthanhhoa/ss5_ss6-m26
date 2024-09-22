<template>
    <div>
      <h1>Sắp xếp mảng số nguyên</h1>
      <button @click="sortAscending">Tăng dần</button>
      <button @click="sortDescending">Giảm dần</button>
  
      <h2>Mảng hiện tại:</h2>
      <ul>
        <li v-for="number in numbers" :key="number">{{ number }}</li>
      </ul>
    </div>
  </template>
  
  <script setup>
  import { ref } from 'vue';
  
  const numbers = ref([5, 3, 8, 1, 2, 7, 4, 6]);
  
  const sortAscending = () => {
    numbers.value.sort((a, b) => a - b);
  };
  
  const sortDescending = () => {
    numbers.value.sort((a, b) => b - a);
  };
  </script>
  
  <style scoped>
  button {
    margin: 5px;
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
  