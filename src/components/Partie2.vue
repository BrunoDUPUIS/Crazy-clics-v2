<script setup>
const emit = defineEmits(['colors'])
</script>
<template>
  <div><button @click="$emit('colors')">Couleur Surprise</button></div>
</template>
<style scoped>
button {
  width: 200px;
  height: 50px;
  border-radius: 50px;
  font-size: 20px;
  background-color: white;
  border: #64c9e6 1px solid;

  color: #64c9e6;
}
</style>
