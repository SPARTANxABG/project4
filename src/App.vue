<script setup>
import { ref } from 'vue';
import TaskInput from './components/TaskInput.vue';
import TaskList from './components/TaskList.vue';
import TaskSummary from './components/TaskSummary.vue';

const tasks = ref([]);

function addTask(taskTitle) {
  tasks.value.push({ title: taskTitle, completed: false });
}

function updateTask({ task, index }) {
  tasks.value.splice(index, 1, task);
}
</script>

<template>
  <div id="app">
    <h1>Task Management App</h1>
    <TaskInput @add-task="addTask" />
    <TaskList :tasks="tasks" @update-task="updateTask" />
    <TaskSummary :tasks="tasks" />
  </div>
</template>