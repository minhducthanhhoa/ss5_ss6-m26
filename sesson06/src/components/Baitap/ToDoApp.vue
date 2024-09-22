<template>
    <div class="todo-app">
      <h1>Todo List</h1>
      <input v-model="newJob" placeholder="Add a new job" />
      <button @click="addJob">Add job</button>
  
      <ul>
        <li v-for="(job, index) in jobs" :key="index">
          <input type="checkbox" v-model="job.completed" />
          <span :class="{ completed: job.completed }">{{ job.title }}</span>
          <button @click="confirmDelete(index)">Delete</button>
        </li>
      </ul>
  
      <p>Completed: {{ completedCount }} / {{ jobs.length }}</p>
  
      <modal v-if="showModal" @confirm="deleteJob" @cancel="showModal = false">
        <p>Bạn có chắc chắn muốn xóa công việc này không?</p>
      </modal>
    </div>
  </template>
  
  <script setup>
  import { ref, reactive, computed } from 'vue';
  
  // Khai báo dữ liệu phản ứng
  const newJob = ref('');
  const jobs = reactive(JSON.parse(localStorage.getItem('todos')) || []); // Lấy dữ liệu từ localStorage
  const showModal = ref(false);
  const jobToDeleteIndex = ref(null);
  
  // Hàm thêm công việc
  const addJob = () => {
    if (newJob.value.trim() === '') return;
    jobs.push({ title: newJob.value, completed: false });
    newJob.value = '';
    saveToLocalStorage();
  };
  
  // Hàm lưu vào localStorage
  const saveToLocalStorage = () => {
    localStorage.setItem('todos', JSON.stringify(jobs));
  };
  
  // Hàm xác nhận xóa
  const confirmDelete = (index) => {
    jobToDeleteIndex.value = index;
    showModal.value = true;
  };
  
  // Hàm xóa công việc
  const deleteJob = () => {
    jobs.splice(jobToDeleteIndex.value, 1);
    showModal.value = false;
    saveToLocalStorage();
  };
  
  // Tính toán số lượng công việc hoàn thành
  const completedCount = computed(() => {
    return jobs.filter(job => job.completed).length;
  });
  </script>
  
  <style scoped>
  .todo-app {
    max-width: 500px;
    margin: auto;
    text-align: center;
  }
  
  .completed {
    text-decoration: line-through;
    color: gray;
  }
  
  button {
    margin-left: 5px;
    padding: 5px 10px;
  }
  
  input {
    margin-bottom: 10px;
    padding: 5px;
  }
  </style>
  