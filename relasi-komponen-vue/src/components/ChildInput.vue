<template>
    <div>
      <input v-model="pesan" placeholder="Tulis pesan..." />
      <button @click="kirim">Kirim</button>
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        pesan: ''
      }
    },
    emits: ['sendMessage'],
    methods: {
      kirim() {
        if (this.pesan.trim()) {
          this.$emit('sendMessage', this.pesan)
          this.pesan = ''
        }
      }
    }
  }
  </script>
  
  <style scoped>
  input {
    padding: 8px;
    margin-right: 10px;
  }
  button {
    background-color: #4CAF50;
    color: white;
    padding: 8px 12px;
    border: none;
    cursor: pointer;
  }
  </style>
  