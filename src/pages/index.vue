<script setup lang="ts">
import { ref } from 'vue'

const menuIsOpen = ref(false)
</script>

<template>
  <button @pointerdown="menuIsOpen=!menuIsOpen">Montrer</button>
  <h1 v-show="menuIsOpen" class="text-2xl">Bonjour monde !</h1>
</template>
