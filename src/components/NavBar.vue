<script setup>
import { RouterLink } from 'vue-router'
</script>

<template>
  <nav class="left-0 top-0 z-50 w-full px-4">
    <div
      class="mx-auto mt-4 h-[80px] w-full max-w-screen border-3 border-black shadow-[8px_8px_0_#000000] text-white flex justify-between items-center px-6 transition-transform duration-300 ease-in-out transform translate-y-0"
    >
      <RouterLink
        to="/"
        class="font-semibold text-3xl tracking-tight transform -rotate-2 hover:rotate-0 transition-transform duration-300 min-w-[80px] xs:min-w-[100px]"
        >Valentin MOREAU</RouterLink
      >
      <div class="hidden md:flex items-center text-base lg:text-lg space-x-6">
        <RouterLink
          class="px-3 py-1 font-bold hover:-translate-y-1 hover:rotate-2 transform transition-all duration-200"
          to="/"
          >Accueil</RouterLink
        >
        <RouterLink
          class="px-3 py-1 font-bold hover:-translate-y-1 hover:rotate-2 transform transition-all duration-200"
          to="/"
          >Parcours</RouterLink
        >
        <RouterLink
          class="px-3 py-1 font-bold hover:-translate-y-1 hover:rotate-2 transform transition-all duration-200"
          to="/"
          >Réalisation</RouterLink
        >
      </div>
      <div class="flex items-center gap-4">
        <div class="relative">
          <a
            href=""
            class="border-3 border-black bg-primary shadow-[8px_8px_0_#000000] inline-flex items-center justify-center whitespace-nowrap h-10 px-4 py-2 hover:shadow-none hover:translate-y-[8px] hover:translate-x-[8px] transition-all"
          >
            Contact</a
          >
        </div>
      </div>
    </div>
  </nav>
</template>
