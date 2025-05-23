<script setup>
import { ref } from 'vue'

const skills = ref([
  { name: 'JavaScript', icon: '/img/cib-javascript.png' },
  { name: 'Php', icon: '/img/cib-php.png' },
  { name: 'Vue', icon: '/img/cib-vue-js.png' },
  { name: 'React', icon: '/img/cib-react.png' },
  { name: 'Laravel', icon: '/img/cib-laravel.png' },
  { name: 'MySQL', icon: '/img/cib-mysql.png' },
  { name: 'Docker', icon: '/img/cib-docker.png' },
  { name: 'Figma', icon: '/img/cib-figma.png' },
  { name: 'VS Code', icon: '/img/cib-visual-studio-code.png' },
  { name: 'Git', icon: '/img/cib-github.png' },
])

const displayedSkills = ref([...skills.value, ...skills.value])
</script>

<template>
  <div
    class="w-full bg-secondary py-4 sm:py-6 overflow-x-hidden border-t-3 border-b-3 border-black z-10"
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
          class="h-8 w-8 sm:h-12 sm:w-12 mr-2 sm:mr-3"
        />
        <span class="text-white text-xl sm:text-3xl font-semibold whitespace-nowrap">{{
          skill.name
        }}</span>
      </div>
    </div>
  </div>
</template>
