<script>
export default {
  name: 'ChatBoard',
  props: {
    messages: {
      type: Array,
      required: true
    }
  }
}
</script>

<template>
  <div class="chatbox">
    <div
      v-for="(message, index) in messages"
      :key="index"
      class="message"
      :class="message.side == 'left' ? 'text-start' : 'text-end'"
    >
      <span class="estilo_nombre">{{ message.name }}</span>
      <p class="message-text rounded" :style="{ backgroundColor: message.color }">
        {{ message.message }}
      </p>
    </div>
  </div>
</template>
<style scoped>
.estilo_nombre {
  font-size: 2rem;
}
</style>
