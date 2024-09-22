<template>
  <div>
    <h1>User component</h1>
    <h3>username: {{userName}}</h3>
    <h3>age: {{age}}</h3>
  </div>
</template>

<script setup>
    // khu vực viết code về js
    const userName = "Nguyễn Văn A";
    const age = 20;
    console.log("userName", userName);
    console.log("age", age);
    
</script>

<style>
</style>