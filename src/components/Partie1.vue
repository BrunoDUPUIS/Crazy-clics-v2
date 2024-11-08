<script setup>
import { wordsList } from '@/utils/data'
const emit = defineEmits(['wordToCorrect'])
</script>
<template>
  <div>
    <button v-for="word in wordsList" :key="word" @click="$emit('wordToCorrect', word)">
      {{ word }}
    </button>
  </div>
</template>
<style scoped>
button {
  background-color: lightgreen;
  padding: 15px;
  border-radius: 10px;
  border: none;
}
div {
  /* border: 1px solid red; */
  display: flex;
  gap: 40px;
}
</style>
