<template>
  <div>
    <h1 v-if="isShow">hiển thị phần tử</h1>
    <h1 v-else>Ẩn phần tử</h1>
    <button @click="handleClick">Toggle</button>
    <h1 v-if="age >= 18">Đủ tuổi</h1>
    <h1 v-else>Chưa đủ tuổi</h1>
    <h3>Tuổi: {{ age }}</h3>
    <button @click="handleIncreaseAge">Tăng tuổi</button>
    <button @click="handleDecreaseAge">Giảm tuổi</button>
    <h1 v-if="role === 'admin'">admin</h1>
    <h1 v-else-if="role === 'user'">User</h1>
    <h1 v-else-if="role === 'edit'">Edit</h1>
    <h1 v-else>other</h1>

    <!-- v-show: hiển thị dữ liệu có điều kiện, tuy nhiên là dữ liệu ko bị xoá khỏi Dom mà nó chỉ bị ẩn đi thông qua display -->
     <h1 v-show="isShowForm">Form content</h1>
  </div>
</template>

<script setup>
import { ref } from 'vue';
    const isShow = ref(false);
    const handleClick = () =>{
        isShow.value = !isShow.value;
    }
    const age = ref(0);
    const handleIncreaseAge = ()=>{
        age.value++;
    }
    const handleDecreaseAge = ()=>{
        age.value--;
    }
    // Tạo 1 biến role cóa giá trị có  thể là admin, user 
    const role = "admin";
    const isShowForm  = ref(true);
    
</script>

<style>

</style>