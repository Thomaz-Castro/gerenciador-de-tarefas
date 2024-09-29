<template>
  <div class="task-list">
    <h2>Gerenciador de Tarefas</h2>

    <div class="task-form">
      <input v-model="newTaskTitle" placeholder="Título da tarefa" />
      <input v-model="newTaskDescription" placeholder="Descrição da tarefa" />
      <button @click="addTask" :disabled="!newTaskTitle || !newTaskDescription">Adicionar Tarefa</button>
    </div>

    <div v-if="tasks.length === 0">
      <p class="no-tasks">Nenhuma tarefa cadastrada. Adicione uma nova tarefa acima!</p>
    </div>

    <transition-group name="task" tag="div">
      <TaskItem
        v-for="task in tasks"
        :key="task.id"
        :task="task"
        @completeTask="completeTask"
      />
    </transition-group>
  </div>
</template>

<script setup>
import { ref } from 'vue';
import TaskItem from './TaskItem.vue';

const tasks = ref([]);
const newTaskTitle = ref('');
const newTaskDescription = ref('');

const addTask = () => {
  if (newTaskTitle.value.trim() && newTaskDescription.value.trim()) {
    tasks.value.push({
      id: tasks.value.length + 1,
      title: newTaskTitle.value,
      description: newTaskDescription.value,
      completed: false
    });
    newTaskTitle.value = '';
    newTaskDescription.value = '';
  }
};

const completeTask = (taskId) => {
  const task = tasks.value.find(t => t.id === taskId);
  if (task) task.completed = true;
};
</script>

<style scoped>
.task-list {
  max-width: 100%;
  margin: 20px auto;
  padding: 20px;
  background-color: #f8f9fa;
  border-radius: 12px;
  box-shadow: 0 4px 10px rgba(0, 0, 0, 0.1);
}

.task-form {
  display: flex;
  flex-direction: column;
  gap: 10px;
  margin-bottom: 20px;
}

input {
  padding: 10px;
  border-radius: 5px;
  border: 1px solid #ddd;
  width: 100%;
}

button {
  padding: 10px;
  background-color: #007bff;
  color: white;
  border: none;
  border-radius: 5px;
  cursor: pointer;
}

button:disabled {
  background-color: gray;
}

.no-tasks {
  text-align: center;
  color: gray;
}
</style>
