<script setup lang="ts">
import { RouterLink, RouterView } from 'vue-router'

</script>

<template>
  <header class="border-2 border-lightBrown bg-lightBlackisBrown p-2 flex justify-center">
    <nav class="flex gap-32 text-lightBrown font-bold">
      <RouterLink class="hover:bg-lightBrown hover:text-lightBlackisBrown p-2" to="/">Home</RouterLink>
      <RouterLink class="hover:bg-lightBrown hover:text-lightBlackisBrown p-2" to="/about">About</RouterLink>
      <RouterLink class="hover:bg-lightBrown hover:text-lightBlackisBrown p-2" to="/projects">Projects</RouterLink>
    </nav>
  </header>
  
  <RouterView />

  <footer class="border-2 border-lightBrown bg-lightBlackisBrown p-4 flex justify-center">
    <p class="text-lightBrown font-bold">By: <span class="font-normal">Mohamed Aymane Jaafouri</span></p>
  </footer>
</template>

