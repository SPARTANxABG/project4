<script setup>
import { defineProps, defineEmits } from 'vue';

const props = defineProps({
  tasks: Array
});

const emit = defineEmits(['update-task']);

function updateTask(task, index) {
  emit('update-task', { task, index });
}
</script>

<template>
  <div>
    <h2>Task List</h2>
    <ul>
      <li v-for="(task, index) in tasks" :key="index">
        <input type="checkbox" v-model="task.completed" @change="updateTask(task, index)">
        <span :class="{ 'completed': task.completed }">{{ task.title }}</span>
      </li>
    </ul>
  </div>
</template>