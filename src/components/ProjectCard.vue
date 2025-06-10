<script setup>
const projects = [
  {
    title: 'Portfolio',
    description: 'Un portfolio en Vue.js 3 avec Tailwind CSS, dans un style néobrutalisme.',
    tags: ['Vue.js 3'],
    githubUrl: 'https://github.com/valmo-dev/valmo-portfolio',
    cover: '/img/portfolio-cover.png',
    isInProgress: false,
  },
  {
    title: 'Survive React',
    description: 'Un mini jeu de gestion de ressources développé en React avec Tailwind CSS.',
    tags: ['React'],
    githubUrl: 'https://github.com/valmo-dev/survive-react',
    cover: '/img/survive-cover.png',
    isInProgress: false,
  },
  {
    title: 'BrutalUI',
    description:
      'Une librairie de composants en cours de développement avec Tailwind CSS et Vue.js 3.',
    tags: ['Vue.js 3'],
    githubUrl: '',
    cover: '',
    isInProgress: true,
  },
]

const getTagIcon = (tag) => {
  const tagLower = tag.toLowerCase()
  if (tagLower.includes('vue')) return '/img/cib-vue-js.png'
  if (tagLower.includes('laravel')) return '/img/cib-laravel.png'
  if (tagLower.includes('mysql')) return '/img/cib-mysql.png'
  if (tagLower.includes('react')) return '/img/cib-react.png'
  return ''
}

const openGithub = (url) => {
  window.open(url, '_blank')
}
</script>

<template>
  <div
    class="w-full max-w-sm h-100 bg-secondary border-3 border-black shadow-[8px_8px_0_#000000] max-h-100 p-4 flex flex-col justify-between mb-12"
    v-for="(project, index) in projects"
    :key="index"
  >
    <div v-if="project.cover" class="w-full h-48 overflow-hidden">
      <img
        :src="project.cover"
        :alt="`Couverture du projet ${project.title}`"
        class="object-cover object-center w-full h-full"
      />
    </div>
    <div
      v-else
      class="w-full h-48 bg-gray-200 border-2 border-dashed border-gray-400 flex items-center justify-center"
    >
      <span class="text-gray-500 font-medium">Projet en cours...</span>
    </div>
    <div class="flex flex-col justify-between gap-3">
      <div class="z-10 flex flex-row justify-between">
        <h1 class="font-bold text-2xl">{{ project.title }}</h1>
        <button
          @click="!project.isInProgress && openGithub(project.githubUrl)"
          :class="[
            'border-3 border-black px-3 py-1 transition-all',
            project.isInProgress
              ? 'bg-gray-400 text-gray-600 cursor-not-allowed shadow-[4px_4px_0_#666666]'
              : 'bg-primary shadow-[4px_4px_0_#000000] cursor-pointer hover:shadow-none hover:translate-y-[4px] hover:translate-x-[4px]',
          ]"
          :disabled="project.isInProgress"
        >
          Voir plus
        </button>
      </div>
      <p class="relative text-base">{{ project.description }}</p>
      <div class="relative flex flex-row items-center gap-4">
        <div
          v-for="(tag, tagIndex) in project.tags"
          :key="tagIndex"
          class="flex items-center gap-2 p-2 font-medium bg-secondary border border-black shadow-[3px_3px_0_#000000] hover:-translate-y-1 hover:rotate-2 hover:scale-115 transition-transform duration-200 ease"
        >
          <img
            v-if="getTagIcon(tag)"
            :src="getTagIcon(tag)"
            :alt="tag"
            class="w-6 h-6 object-contain"
          />
          <span class="font-semibold text-xs">{{ tag }}</span>
        </div>
      </div>
    </div>
  </div>
</template>
