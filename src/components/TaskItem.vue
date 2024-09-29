<template>
  <div class="task-item" :class="{ done: task.completed }">
    <h3>{{ task.title }}</h3>
    <p>{{ task.description }}</p>
    <button @click="markAsCompleted" :disabled="task.completed">
      {{ task.completed ? 'Concluída' : 'Marcar como Concluída' }}
    </button>
  </div>
</template>

<script setup>
import { defineProps, defineEmits } from 'vue';

const props = defineProps({
  task: {
    type: Object,
    required: true
  }
});

const emit = defineEmits(['completeTask']);
const markAsCompleted = () => {
  emit('completeTask', props.task.id);
};
</script>

<style scoped>
.task-item {
  background-color: #ffffff;
  padding: 15px;
  margin-bottom: 10px;
  border-radius: 10px;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
  transition: all 0.3s ease;
}
.task-item:hover {
  transform: translateY(-5px);
}
.task-item.done {
  background-color: #d4edda;
  text-decoration: line-through;
}
button {
  background-color: #28a745;
  border: none;
  color: white;
  padding: 8px 16px;
  border-radius: 5px;
  cursor: pointer;
  transition: background-color 0.3s;
}
button:hover:not(:disabled) {
  background-color: #218838;
}
button:disabled {
  background-color: gray;
}
</style>
