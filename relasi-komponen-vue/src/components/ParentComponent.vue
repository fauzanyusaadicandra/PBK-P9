<template>
    <div>
      <h1>💬 Komunikasi Antar Komponen</h1>
      <ChildInput @sendMessage="handleNewMessage" />
      <div class="card-wrapper">
        <ChildCard
          v-for="(msg, index) in messages"
          :key="index"
          :content="msg"
        >
          <template #footer>
            <p class="card-footer">Pesan ke-{{ index + 1 }}</p>
          </template>
        </ChildCard>
      </div>
    </div>
  </template>
  
  <script>
  import ChildCard from './ChildCard.vue'
  import ChildInput from './ChildInput.vue'
  
  export default {
    components: { ChildCard, ChildInput },
    data() {
      return {
        messages: ['Halo dari Parent!']
      }
    },
    methods: {
      handleNewMessage(pesanBaru) {
        this.messages.push(pesanBaru)
      }
    }
  }
  </script>
  
  <style scoped>
  .card-wrapper {
    display: flex;
    flex-wrap: wrap;
    gap: 16px;
  }
  </style>
  