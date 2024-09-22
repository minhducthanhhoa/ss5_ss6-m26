<template>
    <div>
      <h1>Danh sách các số lẻ</h1>
      <ul>
        <li v-for="number in oddNumbers" :key="number">{{ number }}</li>
      </ul>
    </div>
  </template>
  
  <script setup>
  import { ref, computed } from 'vue';
  
  const numbers = ref([1, 2, 3, 4, 5, 6, 7, 8, 9, 10]);
  
  const oddNumbers = computed(() => {
    return numbers.value.filter(number => number % 2 !== 0);
  });
  </script>
  
  <style scoped>
  h1 {
    font-size: 24px;
    margin-bottom: 10px;
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
  