<script setup>
import Navbar from '../components/NavBar.vue'
import SectionTitle from '../components/SectionTitle.vue'
// import HelloButton from '../components/HelloButton.vue'
import HeroText from '../components/HeroText.vue'
import CircleDecoration from '../components/CircleDecoration.vue'
import HeroAvatar from '@/components/HeroAvatar.vue'
</script>

<template>
  <main class="w-full max-w-7xl mx-auto flex flex-col gap-12 sm:gap-16 md:gap-20 px-4">
    <div
      class="absolute -top-80 scale-75 sm:scale-100 sm:-top-96 md:-top-145 -left-40 sm:-left-32 md:-left-50 z-0"
    >
      <CircleDecoration />
    </div>
    <div class="relative z-10 flex flex-col gap-8 sm:gap-12 md:gap-16">
      <Navbar />
      <SectionTitle />
      <!-- <HelloButton /> -->
      <div class="grid grid-cols-1 md:grid-cols-3 items-center gap-6 md:gap-8 lg:gap-12">
        <div class="col-span-2">
          <HeroText class="order-2 md:order-1" />
        </div>
        <div class="col-span-1">
          <HeroAvatar class="order-1 md:order-2" />
        </div>
      </div>
    </div>
  </main>
</template>
