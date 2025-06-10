<script setup>
import { ref, computed } from 'vue'

const activeTab = ref('work')

const workExperience = [
  {
    company: "Lab'Science",
    logo: '/img/labscience.png',
    role: 'Développeur Fullstack',
    period: '2023 - 2025',
    description: "Développement d'application web pour des outils internes.",
    tags: ['Vue.js 3', 'Laravel', 'PHP', 'JavaScript', 'Docker', 'MySQL'],
  },
  {
    company: 'Armée de Terre',
    logo: '/img/army.svg',
    role: "Chef d'engin, Chef de groupe (8 pers.), Chef d'équipe (3 pers.)",
    description:
      "Gestion d'un véhicule de combat, et d'une équipe de 3 personnes la plupart du temps. Gestion d'un groupe de 8 personnes quelques fois.",
    period: '2018 - 2023',
  },
]

const educations = [
  {
    school: 'CEFIM',
    logo: '/img/cefim.png',
    degree: 'Concepteur Développeur d’Applications',
    period: '2024 - 2025',
    description:
      'Apprentissage de la gestion de projet, des bonnes pratiques et des outils pour concevoir et développer des applications web modernes.',
    tags: ['Méthodes Agiles', 'Docker', 'Git'],
  },
  {
    school: 'CEFIM',
    logo: '/img/cefim.png',
    degree: 'Développeur Web',
    period: '2023 - 2024',
    description: 'Apprentissage de la création d’applications web modernes.',
    tags: ['React', 'Symfony', 'PHP', 'JavaScript', 'MySQL'],
  },
]

const processItems = (items, type) => {
  return items.map((item, index) => ({
    ...item,
    processedLogo: item.logo,
    uniqueKey: `${type}-${(item.company || item.school || 'item').replace(/\s+/g, '-')}-${index}`,
  }))
}

const processedWorkExperience = computed(() => processItems(workExperience, 'work'))
const processedEducations = computed(() => processItems(educations, 'education'))
</script>

<template>
  <section id="experience" class="z-10">
    <div
      class="w-[90%] max-w-7xl mx-auto p-2 border-3 border-black shadow-[8px_8px_0_#000000] bg-background-primary"
    >
      <!-- Onglets -->
      <div class="flex flex-col md:flex-row gap-2 items-center mb-8">
        <button
          @click="activeTab = 'work'"
          :class="[
            ' w-full py-4 px-6 text-2xl font-semibold focus:outline-none transition-colors duration-200 ease-in-out cursor-pointer',
            activeTab === 'work'
              ? 'bg-secondary text-white  relative z-10'
              : 'bg-background-primary text-neutral-400 hover:text-white hover:bg-neutral-800/60',
          ]"
        >
          Travail
        </button>
        <button
          @click="activeTab = 'education'"
          :class="[
            'w-full py-4 px-6 text-2xl font-semibold focus:outline-none transition-colors duration-200 ease-in-out cursor-pointer',
            activeTab === 'education'
              ? 'bg-secondary text-white  relative z-10'
              : 'bg-background-primary text-neutral-400 hover:text-white hover:bg-neutral-800/60',
          ]"
        >
          École
        </button>
      </div>

      <!-- Panneau de Contenu des Onglets -->
      <div class="p-6 sm:p-8 relative m-12">
        <!-- Contenu Expérience Professionnelle -->
        <div v-show="activeTab === 'work'">
          <h3 class="text-xl font-semibold mb-6 sm:mb-8">Expérience professionnelle</h3>
          <ul class="space-y-8">
            <li
              v-for="job in processedWorkExperience"
              :key="job.uniqueKey"
              class="flex flex-col justify-center items-center md:grid md:grid-cols-[.5fr_.7fr_3fr] gap-2 sm:gap-x-6 gap-y-4 pb-8 border-b border-black/50 last:border-b-0 last:pb-0"
            >
              <div class="w-full sm:w-36 text-center text-2xl opacity-70">
                {{ job.period }}
              </div>

              <div class="sm:mt-0">
                <img
                  v-if="job.processedLogo"
                  :src="job.processedLogo"
                  :alt="job.company"
                  class="w-full max-w-40 md:max-w-50 object-contain"
                />
                <div
                  v-else
                  class="w-20 rounded-md bg-secondary flex items-center justify-center shadow-sm"
                >
                  <svg
                    xmlns="http://www.w3.org/2000/svg"
                    fill="none"
                    viewBox="0 0 24 24"
                    stroke-width="1.5"
                    stroke="currentColor"
                    class="w-10 h-10"
                  >
                    <path
                      stroke-linecap="round"
                      stroke-linejoin="round"
                      d="M2.25 21h19.5m-18-18v18A2.25 2.25 0 004.5 21h15a2.25 2.25 0 002.25-2.25V5.25A2.25 2.25 0 0019.5 3H4.5A2.25 2.25 0 002.25 5.25v18zm11.06-7.94c.39-.39 1.02-.39 1.41 0l2.25 2.25a.75.75 0 01-1.06 1.06L13.5 15.06l-2.19 2.19a.75.75 0 01-1.06-1.06l2.25-2.25zM10.5 12a1.5 1.5 0 11-3 0 1.5 1.5 0 013 0z"
                    />
                  </svg>
                </div>
              </div>

              <div class="flex-grow mt-1 sm:mt-0">
                <h4 class="text-lg font-semibold text-white uppercase tracking-wide">
                  {{ job.company }}
                </h4>
                <p class="text-md font-semibold mt-0.5 uppercase opacity-80">
                  {{ job.role }}
                </p>
                <p class="text-sm mt-3">{{ job.description }}</p>
                <div v-if="job.tags && job.tags.length" class="mt-4 flex flex-wrap gap-3">
                  <span
                    v-for="tag in job.tags"
                    :key="tag"
                    class="px-3 py-1 text-xs font-medium bg-secondary border border-black shadow-[3px_3px_0_#000000] hover:-translate-y-1 hover:rotate-2 hover:scale-115 transition-transform duration-200 ease-in-out"
                  >
                    {{ tag }}
                  </span>
                </div>
              </div>
            </li>
          </ul>
        </div>

        <!-- Contenu Parcours Scolaire -->
        <div v-show="activeTab === 'education'">
          <h3 class="text-xl font-semibold mb-6 sm:mb-8">Parcours scolaire</h3>
          <ul class="space-y-8">
            <li
              v-for="education in processedEducations"
              :key="education.uniqueKey"
              class="flex flex-col justify-center items-center md:grid md:grid-cols-[.5fr_.7fr_3fr] gap-2 sm:gap-x-6 gap-y-4 pb-8 border-b border-black/50 last:border-b-0 last:pb-0"
            >
              <div class="w-full sm:w-36 text-center text-2xl opacity-70">
                {{ education.period }}
              </div>
              <div class="sm:mt-0">
                <img
                  v-if="education.processedLogo"
                  :src="education.processedLogo"
                  :alt="education.school"
                  class="w-full max-w-40 md:max-w-50 object-contain"
                />
                <div v-else class="w-20 h-20 flex items-center justify-center shadow-sm">
                  <svg
                    xmlns="http://www.w3.org/2000/svg"
                    fill="none"
                    viewBox="0 0 24 24"
                    stroke-width="1.5"
                    stroke="currentColor"
                    class="w-10 h-10"
                  >
                    <path
                      stroke-linecap="round"
                      stroke-linejoin="round"
                      d="M4.26 10.147a60.436 60.436 0 00-.491 6.347A48.627 48.627 0 0112 20.904a48.627 48.627 0 018.232-4.41 60.46 60.46 0 00-.491-6.347m-15.482 0a50.57 50.57 0 00-2.658-.813A59.905 59.905 0 0112 3.493a59.902 59.902 0 0110.399 5.84c-.896.248-1.783.52-2.658.814m-15.482 0A50.697 50.697 0 0112 13.489a50.702 50.702 0 017.74-3.342M6.75 15a.75.75 0 100-1.5.75.75 0 000 1.5zm0 0v-3.675A55.378 55.378 0 0112 8.443m-7.007 11.55A5.981 5.981 0 006.75 15.75v-1.5"
                    />
                  </svg>
                </div>
              </div>
              <div class="flex-grow mt-1 sm:mt-0">
                <h4 class="text-lg font-semibold text-white uppercase tracking-wide">
                  {{ education.school }}
                </h4>
                <p class="text-md font-semibold mt-0.5 uppercase opacity-80">
                  {{ education.degree }}
                </p>
                <p class="text-sm mt-3">
                  {{ education.description }}
                </p>
                <div
                  v-if="education.tags && education.tags.length"
                  class="mt-4 flex flex-wrap gap-2"
                >
                  <span
                    v-for="tag in education.tags"
                    :key="tag"
                    class="px-3 py-1 text-xs font-medium bg-secondary border border-black shadow-[3px_3px_0_#000000] hover:-translate-y-1 hover:rotate-2 hover:scale-115 transition-transform duration-200 ease-in-out"
                  >
                    {{ tag }}
                  </span>
                </div>
              </div>
            </li>
          </ul>
        </div>
      </div>
    </div>
  </section>
</template>
