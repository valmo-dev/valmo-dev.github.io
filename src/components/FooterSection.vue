<script setup>
const scrollToSection = (sectionId) => {
  const section = document.getElementById(sectionId)
  if (section) {
    section.scrollIntoView({ behavior: 'smooth', block: 'start' })
  }
}
</script>

<template>
  <footer class="w-full p-8 border-t-8 border-black z-10">
    <div class="mx-auto max-w-7xl">
      <div class="grid grid-cols-1 md:grid-cols-3 gap-6 mb-12">
        <div>
          <h3 class="text-2xl mb-4 uppercase tracking-wider font-bold">Liens rapides</h3>
          <ul class="space-y-3">
            <li>
              <a
                @click="scrollToSection('hero')"
                class="px-3 py-1 font-bold hover:-translate-y-1 hover:rotate-2 transform transition-all duration-200 cursor-pointer"
                >Accueil</a
              >
            </li>
            <li>
              <a
                @click="scrollToSection('experience')"
                class="px-3 py-1 font-bold hover:-translate-y-1 hover:rotate-2 transform transition-all duration-200 cursor-pointer"
                >Parcours</a
              >
            </li>
            <li>
              <a
                @click="scrollToSection('projects')"
                class="px-3 py-1 font-bold hover:-translate-y-1 hover:rotate-2 transform transition-all duration-200 cursor-pointer"
                >Réalisation</a
              >
            </li>
          </ul>
        </div>
      </div>
      <div class="pt-8 flex flex-col md:flex-row justify-between items-center gap-4">
        <p class="font-semibold text-xl flex flex-row items-center gap-3">
          <span class="text-3xl">©</span>
          <span>2025</span>
          <span>Valentin MOREAU</span>
        </p>
        <div
          class="bg-background-primary border-3 border-black shadow-[8px_8px_0_#000000] px-4 py-2 font-mono font-semibold text-lg"
        >
          Code with Vue.js 3 + Tailwind
        </div>
      </div>
    </div>
  </footer>
</template>
