<template>
    <div>
      <h1>Quyền của người dùng:</h1>
      <div v-if="userRole === 'admin'">
        <p>Quyền hạn của bạn là: Admin</p>
      </div>
      <div v-else-if="userRole === 'user'">
        <p>Quyền hạn của bạn là: User</p>
      </div>
      <div v-else-if="userRole === 'guest'">
        <p>Quyền hạn của bạn là: Guest</p>
      </div>
      <div v-else>
        <p>Không xác định quyền người dùng.</p>
      </div>
    </div>
  </template>
  
  <script setup>
  import { ref } from 'vue';
  
 
  const userRole = ref('guest');
  </script>
  
  <style scoped>
  h1 {
    font-size: 24px;
    margin-bottom: 10px;
  }
  p {
    font-size: 18px;
    color: #333;
  }
  </style>
  