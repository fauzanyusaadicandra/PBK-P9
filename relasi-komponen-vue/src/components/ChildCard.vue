<template>
    <div class="card">
      <p>{{ content }}</p>
      <slot name="footer"></slot>
    </div>
  </template>
  
  <script>
  export default {
    props: ['content']
  }
  </script>
  
  <style scoped>
  .card {
    background: #f9f9f9;
    padding: 20px;
    border-radius: 12px;
    width: 200px;
    transition: transform 0.2s;
  }
  .card:hover {
    transform: scale(1.05);
    background-color: #e0f7fa;
  }
  .card-footer {
    font-size: 12px;
    color: #555;
  }
  </style>
  