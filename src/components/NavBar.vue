<script setup>
import { ref } from 'vue'

const isMobileMenuOpen = ref(false)

const toggleMobileMenu = () => {
  isMobileMenuOpen.value = !isMobileMenuOpen.value
}

const scrollToSection = (sectionId) => {
  const section = document.getElementById(sectionId)
  if (section) {
    section.scrollIntoView({ behavior: 'smooth', block: 'start' })
  }
}
</script>

<template>
  <nav class="left-0 top-0 z-50 w-full px-4">
    <div
      class="mx-auto mt-4 h-[80px] w-full max-w-screen bg-background-primary border-3 border-black shadow-[8px_8px_0_#000000] text-white flex justify-between items-center px-6 transition-transform duration-300 ease-in-out transform translate-y-0"
    >
      <a
        @click="scrollToSection('hero')"
        class="font-semibold text-xl sm:text-2xl lg:text-3xl tracking-tight transform -rotate-2 hover:rotate-0 transition-transform duration-300 min-w-[80px] xs:min-w-[100px]"
        >Valentin MOREAU</a
      >
      <div class="hidden md:flex items-center text-base lg:text-lg space-x-6">
        <a
          @click="scrollToSection('hero')"
          class="px-3 py-1 font-bold hover:-translate-y-1 hover:rotate-2 transform transition-all duration-200 cursor-pointer"
          >Accueil</a
        >
        <a
          @click="scrollToSection('experience')"
          class="px-3 py-1 font-bold hover:-translate-y-1 hover:rotate-2 transform transition-all duration-200 cursor-pointer"
          >Parcours</a
        >
        <a
          @click="scrollToSection('projects')"
          class="px-3 py-1 font-bold hover:-translate-y-1 hover:rotate-2 transform transition-all duration-200 cursor-pointer"
          >Mes projets</a
        >
      </div>
      <div class="flex items-center gap-4">
        <div class="hidden md:block relative">
          <a
            href="mailto:valmo.dev@gmail.com"
            class="border-3 border-black bg-primary shadow-[8px_8px_0_#000000] inline-flex items-center justify-center whitespace-nowrap h-10 px-4 py-2 hover:shadow-none hover:translate-y-[8px] hover:translate-x-[8px] transition-all"
          >
            Contact</a
          >
        </div>
        <div class="md:hidden">
          <button
            @click="toggleMobileMenu"
            class="text-white focus:outline-none relative w-8 h-8"
            aria-label="Toggle menu"
          >
            <svg
              v-if="!isMobileMenuOpen"
              class="w-8 h-8"
              fill="none"
              stroke="currentColor"
              viewBox="0 0 24 24"
              xmlns="http://www.w3.org/2000/svg"
            >
              <path
                stroke-linecap="round"
                stroke-linejoin="round"
                stroke-width="2"
                d="M4 6h16M4 12h16M4 18h16"
              ></path>
            </svg>
            <svg
              v-else
              class="w-8 h-8"
              fill="none"
              stroke="currentColor"
              viewBox="0 0 24 24"
              xmlns="http://www.w3.org/2000/svg"
            >
              <path
                stroke-linecap="round"
                stroke-linejoin="round"
                stroke-width="2"
                d="M6 18L18 6M6 6l12 12"
              ></path>
            </svg>
          </button>
        </div>
      </div>
    </div>
    <div
      v-if="isMobileMenuOpen"
      class="md:hidden mt-2 absolute top-[calc(1rem+100px)] left-4 right-4 mx-auto z-40 bg-secondary border-3 border-black shadow-[8px_8px_0_#000000]"
    >
      <a
        class="block px-4 py-3 text-white hover:bg-primary cursor-pointer"
        @click="toggleMobileMenu && scrollToSection('hero')"
        >Accueil</a
      >
      <a
        class="block px-4 py-3 text-white hover:bg-primary cursor-pointer"
        @click="toggleMobileMenu && scrollToSection('experience')"
        >Parcours</a
      >
      <a
        class="block px-4 py-3 text-white hover:bg-primary cursor-pointer"
        @click="toggleMobileMenu && scrollToSection('projects')"
        >Réalisation</a
      >
      <a
        href="mailto:valmo.dev@gmail.com"
        class="block px-4 py-3 text-white bg-primary hover:bg-opacity-70 font-bold text-center cursor-pointer"
        >Contact</a
      >
    </div>
  </nav>
</template>
