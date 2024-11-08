<script setup>
import { numbersList } from '@/utils/data'
const emit = defineEmits(['numberOfKms'])
</script>
<template>
  <div>
    <button v-for="kms in numbersList" :key="kms" @click="$emit('numberOfKms', kms)">
      {{ kms }} km
    </button>
  </div>
</template>
<style scoped>
button {
  background-color: rgb(214, 123, 214);
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
