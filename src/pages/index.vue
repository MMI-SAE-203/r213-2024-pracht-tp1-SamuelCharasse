<script setup lang="ts">
import { ref } from 'vue'

const maVar = ref(false)
console.log('maVar : ', maVar.value)
</script>

<template>
  <button @pointerdown="maVar=!maVar">Montrer</button>
  <h1 v-show="maVar" class="text-2xl">Bonjour monde !</h1>
</template>
