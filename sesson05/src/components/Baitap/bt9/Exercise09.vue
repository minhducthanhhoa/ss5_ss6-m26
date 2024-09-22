<template>
    <div>
      <h1>Giới tính ngẫu nhiên</h1>
      <p>Giới tính hiện tại: {{ currentGender }}</p>
      <button @click="randomizeGender">Random gender</button>
    </div>
  </template>
  
  <script setup>
  import { ref } from 'vue';
  
  // Mảng chứa các giới tính
  const genders = ['Nam', 'Nữ', 'Khác'];
  
  // Biến lưu giới tính hiện tại, khởi tạo là "Nam"
  const currentGender = ref('Nam');
  
  const randomizeGender = () => {
    const randomIndex = Math.floor(Math.random() * genders.length);
    currentGender.value = genders[randomIndex];
  };
  </script>
  
  <style scoped>
  button {
    margin-top: 10px;
    padding: 10px;
    font-size: 16px;
    cursor: pointer;
  }
  
  p {
    font-size: 18px;
    margin: 10px 0;
  }
  </style>
  