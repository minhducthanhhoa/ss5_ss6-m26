<template>
    <div>
      <button @click="toggleShow">Click to show</button>
      <p v-if="isShow">Rikkei Education</p>
    </div>
  </template>
  
  <script lang="ts">
  import { ref } from 'vue';  
  
  const Exercise01 = {
    setup() {
      const isShow = ref(false);
  
      const toggleShow = () => {
        isShow.value = true;
      };
  
      return {
        isShow,
        toggleShow,
      };
    },
  };
  
  export default Exercise01;
  </script>
  
  <style scoped>
  /* Thêm style nếu cần */
  </style>
  