<script setup>
import { ref } from 'vue'

const skills = ref([
  { name: 'JavaScript', icon: '../assets/img/cib-javascript.png' },
  { name: 'Php', icon: '../assets/img/cib-php.png' },
  { name: 'Vue', icon: '../assets/img/cib-vue-js.png' },
  { name: 'React', icon: '../assets/img/cib-react.png' },
  { name: 'Laravel', icon: '../assets/img/cib-laravel.png' },
  { name: 'MySQL', icon: '../assets/img/cib-mysql.png' },
  { name: 'Docker', icon: '../assets/img/cib-docker.png' },
  { name: 'Figma', icon: '../assets/img/cib-figma.png' },
  { name: 'VS Code', icon: '../assets/img/cib-visual-studio-code.png' },
  { name: 'Git', icon: '../assets/img/cib-github.png' },
])

const displayedSkills = ref([...skills.value, ...skills.value])
</script>

<template>
  <div
    class="w-full bg-secondary py-4 sm:py-6 overflow-x-hidden border-t-3 border-b-3 border-black"
  >
    <div class="flex animate-infinite-scroll group hover:animation-pause">
      <div
        v-for="(skill, index) in displayedSkills"
        :key="`skill-${index}`"
        class="flex items-center mx-4 sm:mx-6 flex-shrink-0"
      >
        <img
          v-if="skill.icon"
          :src="skill.icon"
          :alt="skill.name"
          class="h-6 w-6 sm:h-8 sm:w-8 mr-2 sm:mr-3"
        />
        <span class="text-white text-lg sm:text-xl font-semibold whitespace-nowrap">{{
          skill.name
        }}</span>
      </div>
    </div>
  </div>
</template>
