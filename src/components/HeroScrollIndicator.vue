<script setup>
import { ref, onMounted } from 'vue'

const isVisible = ref(true)

const handleScroll = () => {
  const heroSection = document.getElementById('hero')
  if (heroSection) {
    const heroBottom = heroSection.offsetTop + heroSection.offsetHeight
    const scrollPosition = window.pageYOffset + window.innerHeight

    isVisible.value = scrollPosition <= heroBottom + 130
  }
}

onMounted(() => {
  window.addEventListener('scroll', handleScroll)
  document.documentElement.style.scrollBehavior = 'smooth'
})
</script>

<template>
  <div
    v-show="isVisible"
    class="hidden fixed bottom-8 transform z-20 animate-pulse lg:flex items-center justify-center flex-col"
  >
    <button
      @click="scrollToNextSection"
      class="border-3 border-black p-3 bg-primary transition-all fade"
    >
      <div class="relative">
        <svg
          xmlns="http://www.w3.org/2000/svg"
          width="24"
          height="24"
          viewBox="0 0 24 24"
          fill="none"
          stroke="currentColor"
          stroke-width="3"
          stroke-linecap="round"
          stroke-linejoin="round"
          class="text-white transition-transform duration-300 group-hover:translate-y-1 z-10"
        >
          <polyline points="6 9 12 15 18 9"></polyline>
        </svg>
      </div>
    </button>
  </div>
</template>
