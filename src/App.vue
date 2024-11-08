<script setup>
import { ref } from 'vue'
import Partie1 from './components/Partie1.vue'
import Partie2 from './components/Partie2.vue'
import Partie3 from './components/Partie3.vue'
import { colorsList } from './utils/data'
const result = ref('')
const wordToCorrect = (word) => {
  const firstLetter = word[0].toUpperCase()
  const othersLetters = word.slice(1).toLowerCase()
  result.value = firstLetter + othersLetters
}
const colors = () => {
  const randomIndex = Math.floor(Math.random() * colorsList.length)
  result.value = colorsList[randomIndex]
}
const numberOfKms = (kms) => {
  const kmsInCent = kms * 100000

  result.value = kms + ' kms = ' + kmsInCent + ' cm'
}
</script>

<template>
  <main>
    <h1>Crazy clics v2</h1>
    <section>
      <div class="buttons">
        <Partie1 @wordToCorrect="wordToCorrect" />
        <Partie2 @colors="colors" />
        <Partie3 @numberOfKms="numberOfKms" />
      </div>
      <div class="result">
        <h2>👇 Le Résultat 👇</h2>
        <p>{{ result }}</p>
      </div>
    </section>
  </main>
</template>

<style scoped>
section {
  /* border: 1px solid red; */
  display: flex;
  justify-content: center;
  align-items: center;
}
.buttons {
  /* border: 2px solid green; */
  width: 50%;
  display: flex;
  flex-direction: column;
  align-items: center;
}
.result {
  text-align: center;
  width: 50%;
}
div {
  /* border: 1px solid blue; */
  padding: 30px;
  display: flex;
}
h1 {
  margin-top: 30px;
  text-align: center;
  font-size: 50px;
  font-weight: bold;
}
.result {
  /* border: 1px solid yellow; */
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 10px;
}
p {
  border: 1px solid black;
  width: 200px;
  height: 30px;
  display: flex;
  justify-content: center;
  align-items: center;
}
h2 {
  font-weight: bold;
  font-size: 20px;
}
</style>
