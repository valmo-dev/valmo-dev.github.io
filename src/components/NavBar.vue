<script setup>
import { RouterLink } from 'vue-router'
</script>

<template>
  <nav
    class="w-full max-w-7xl border-3 border-black shadow-[10px_10px_0_#000000] mx-auto text-white flex flex-row justify-between items-center py-6 px-8"
  >
    <RouterLink to="/" class="font-semibold text-3xl">Valentin MOREAU</RouterLink>
    <div class="flex flex-row gap-4">
      <RouterLink to="/">Accueil</RouterLink>
      <RouterLink to="/">Parcours</RouterLink>
      <RouterLink to="/">Réalisation</RouterLink>
    </div>
    <a href="" class="border-3 border-black bg-primary shadow-[8px_8px_0_#000000] px-5"> Contact</a>
  </nav>
</template>
