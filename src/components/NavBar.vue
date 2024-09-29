<template>
    <nav class="navbar">
      <div class="logo">Gestor de Tarefas</div>
      <ul>
        <li><a href="#">Início</a></li>
        <li><a href="#">Sobre</a></li>
        <li><a href="#">Contato</a></li>
      </ul>
    </nav>
  </template>
  
  <script setup></script>
  
  <style scoped>
  .navbar {
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 10px 20px;
    background-color: #007bff;
    color: white;
  }
  .logo {
    font-size: 1.5rem;
    font-weight: bold;
  }
  ul {
    list-style-type: none;
    display: flex;
    gap: 15px;
  }
  li a {
    color: white;
    text-decoration: none;
    font-size: 1.1rem;
  }
  @media (max-width: 600px) {
    .navbar {
      flex-direction: column;
      align-items: flex-start;
    }
    ul {
      padding-left: 0;
    }
  }
  </style>
  