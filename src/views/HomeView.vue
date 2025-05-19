<script setup>
import Navbar from '../components/NavBar.vue'
import SectionTitle from '../components/SectionTitle.vue'
// import HelloButton from '../components/HelloButton.vue'
import HeroText from '../components/HeroText.vue'
import CircleDecoration from '../components/CircleDecoration.vue'
import HeroAvatar from '@/components/HeroAvatar.vue'
import SkillsBar from '@/components/SkillsBar.vue'
</script>

<template>
  <main
    class="relative flex min-h-[100vh] w-full flex-col items-center bg-background-primary bg-[linear-gradient(to_right,#80808033_1px,transparent_1px),linear-gradient(to_bottom,#80808033_1px,transparent_1px)] bg-[size:70px_70px] pt-24 lg:pt-0"
  >
    <div
      class="absolute -top-80 scale-75 sm:scale-100 sm:-top-96 md:-top-145 -left-40 sm:-left-32 md:-left-50 z-0"
    >
      <CircleDecoration />
    </div>
    <!-- <div class="relative z-10 flex flex-col gap-8 sm:gap-12 md:gap-16"> -->
    <!-- <HelloButton /> -->
    <Navbar class="top-0 w-full max-w-7xl" />
    <SectionTitle />
    <div
      class="mx-auto w-full max-w-7xl px-5 py-10 md:py-20 text-left flex flex-col lg:flex-row items-center z-10"
    >
      <div class="w-full lg:w-1/2 mt-8 md:mt-0 flex flex-col items-center lg:items-start lg:ml-8">
        <HeroText />
      </div>
      <div class="w-full lg:w-1/2 md:mt-6 lg:mt-0 flex justify-center lg:pl-12">
        <HeroAvatar />
      </div>
    </div>
    <!-- </div> -->
  </main>
  <SkillsBar />
</template>
