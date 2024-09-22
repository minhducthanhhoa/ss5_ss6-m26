<template>
    <div>
      <h1>Chọn Button</h1>
      <div>
        <button
          v-for="index in 3"
          :key="index"
          :class="{ active: activeIndex === index }"
          @click="setActive(index)"
        >
          Button {{ index }}
        </button>
      </div>
    </div>
  </template>
  
  <script setup>
  import { ref } from 'vue';
  
  const activeIndex = ref(1);
  
  const setActive = (index) => {
    activeIndex.value = index;
  };
  </script>
  
  <style scoped>
  button {
    margin: 5px;
    padding: 10px;
    font-size: 16px;
    cursor: pointer;
  }
  
  .active {
    background-color: red;
    color: #fff;
  }
  </style>
  