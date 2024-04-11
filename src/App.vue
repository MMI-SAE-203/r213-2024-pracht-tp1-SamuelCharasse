<script setup lang="ts">
import { onErrorCaptured } from 'vue'
import { RouterLink, RouterView } from 'vue-router/auto'
import { ref } from 'vue'

const menuIsOpen = ref(false)
onErrorCaptured((err, instance, info) => {
  console.error('erreur : ', err, '\ninfo : ', info, '\ncomposant : ', instance)
  return true
})
</script>

<template>
  <header>
    <button
      @pointerdown="menuIsOpen = !menuIsOpen"
      aria-controls="mainNav"
      aria-expanded="true"
      class="rounded-full border-2 border-indigo-500 bg-indigo-200 px-2"
    >
    menu
    </button>
    <Transition
    class="transition-transform duration-300"
    enter-from-class="-translate-x-full"
    enter-to-class="translate-x-0"
    leave-active-class="-translate-x-full"
  >
    <nav v-show="menuIsOpen" id="mainNav" class="bg-cyan-500/50 w-32 rounded-r-lg text-center hover:bg-cyan-500">
      <ul>
        <li><RouterLink to="/">Accueil</RouterLink></li>
        <li><RouterLink to="/accordeon">Accordéon</RouterLink></li>
        <li><RouterLink to="/boucle">Boucle</RouterLink></li>
      </ul>
    </nav>
  </Transition>   
  </header>
  <RouterView v-slot="{ Component }">
    <Suspense>
      <component :is="Component" />
    </Suspense>
  </RouterView>
</template>
