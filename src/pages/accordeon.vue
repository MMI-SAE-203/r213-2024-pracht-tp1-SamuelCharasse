<script setup lang="ts">
    import { ref } from 'vue'
    const sectionOpen = ref(0)
</script>
<template>
<section>
  <button class="text-xl" @pointerdown="sectionOpen = sectionOpen === 1 ? 0 : 1">bouton 1</button>
  <p v-show="sectionOpen === 1">loren...</p>
</section>
<section>
    <button class="text-xl" @pointerdown="sectionOpen = sectionOpen === 2 ? 0 : 2">bouton 2</button>
    <p v-show="sectionOpen === 2">Rerum sint tempore cupiditate asperiores incidunt totam animi corrupti nam debitis aspernatur ut magni error perferendis consequatur molestiae illo, sed dolores, cum laboriosam. Numquam, commodi animi? Dolorum aliquam quam inventore.</p>
</section>
<section>
    <button class="text-xl" @pointerdown="sectionOpen = sectionOpen === 3 ? 0 : 3">bouton 3</button>
    <p v-show="sectionOpen === 3">Impedit fugit labore quis aperiam! Hic illum ipsa atque dolorem officiis molestias dicta eum illo blanditiis optio explicabo nihil voluptate quasi molestiae cum at maiores, laborum earum mollitia dolor dignissimos.</p>
</section>  
</template>
