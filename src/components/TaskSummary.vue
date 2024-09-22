<script setup>
import { computed } from 'vue';
import { defineProps } from 'vue';

const props = defineProps({
  tasks: Array
});

const totalTasks = computed(() => props.tasks.length);
const completedTasks = computed(() => props.tasks.filter(task => task.completed).length);
</script>

<template>
  <div>
    <h2>Task Summary</h2>
    <p>Total Tasks: {{ totalTasks }}</p>
    <p>Completed Tasks: {{ completedTasks }}</p>
  </div>
</template>