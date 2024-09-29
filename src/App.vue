<template>
  <div class="app-container">
    <NavBar />
    <main>
      <TaskList />
    </main>
    <FooterBar />
  </div>
</template>

<script setup>
import NavBar from './components/NavBar.vue';
import TaskList from './components/TaskList.vue';
import FooterBar from './components/FooterBar.vue';
</script>

<style>
@import './assets/styles.css';  
</style>