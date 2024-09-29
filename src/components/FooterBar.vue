<template>
    <footer class="footer">
      <p>&copy; 2024 Gestor de Tarefas | Todos os direitos reservados</p>
    </footer>
  </template>
  
  <script setup></script>
  
  <style scoped>
 .footer {
  background-color: #007bff; /* Cor de fundo do footer */
  padding: 10px; /* Espaçamento interno */
  text-align: center; /* Alinhamento do texto */
  color: white; /* Cor do texto */
  position: fixed; /* Posição fixa na parte inferior */
  left: 0; /* Alinhar à esquerda */
  right: 0; /* Alinhar à direita */
  bottom: 0; /* Fixo na parte inferior */
  z-index: 1000; /* Garantir que esteja acima de outros elementos */
}

.container {
  padding-bottom: 50px; /* Espaçamento na parte inferior para evitar que o conteúdo fique atrás do footer */
}

  </style>
  