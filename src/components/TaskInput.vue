<script setup>
import { ref } from 'vue';
import { defineEmits } from 'vue';

const newTask = ref('');
const emit = defineEmits(['add-task']);

function addTask() {
  if (newTask.value.trim()) {
    emit('add-task', newTask.value);
    newTask.value = '';
  }
}
</script>

<template>
  <div>
    <h2>Add Task</h2>
    <input v-model="newTask" @keyup.enter="addTask" placeholder="Enter task">
    <button @click="addTask">Add Task</button>
  </div>
</template>