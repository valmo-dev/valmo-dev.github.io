<script setup>
import Navbar from '@/components/NavBar.vue'
import HeroScrollIndicator from '@/components/HeroScrollIndicator.vue'
import HeroTitle from '@/components/HeroTitle.vue'
import SectionTitle from '@/components/SectionTitle.vue'
import HeroText from '@/components/HeroText.vue'
// import CircleDecoration from '@/components/CircleDecoration.vue'
import HeroAvatar from '@/components/HeroAvatar.vue'
import BackToTop from '@/components/BackToTop.vue'
import StorySection from '@/components/StorySection.vue'
import SkillsBar from '@/components/SkillsBar.vue'
import ExperienceTimeline from '@/components/ExperienceTimeline.vue'
import ProjectCard from '@/components/ProjectCard.vue'
import Footer from '@/components/FooterSection.vue'
</script>

<template>
  <div
    class="min-h-screen opacity-100 transition-opacity duration-300 bg-background-primary font-primary font-normal text-white"
  >
    <main
      class="relative flex min-h-screen w-full flex-col items-center justify-between bg-background-primary bg-[linear-gradient(to_right,#80808033_1px,transparent_1px),linear-gradient(to_bottom,#80808033_1px,transparent_1px)] bg-[size:70px_70px] pt-6 lg:pt-0 gap-4"
    >
      <HeroScrollIndicator />
      <!-- <div
        class="absolute -top-80 scale-75 sm:scale-100 sm:-top-96 md:-top-145 -left-40 sm:-left-32 md:-left-50"
      >
        <CircleDecoration color="secondary" />
      </div> -->

      <Navbar class="top-0 w-full max-w-7xl place-self-center" />
      <section id="hero" class="w-full z-10 flex flex-col justify-between">
        <HeroTitle firstTitle="Developpeur" secondTitle="Fullstack" />
        <div
          class="mx-auto w-full max-w-7xl px-5 py-8 md:py-12 text-left flex flex-col lg:flex-row items-center z-10"
        >
          <div
            class="w-full lg:w-1/2 mt-8 md:mt-0 flex flex-col items-center lg:items-start lg:ml-8"
          >
            <HeroText />
          </div>
          <div class="w-full lg:w-1/2 md:mt-6 lg:mt-0 flex justify-center lg:pl-12">
            <HeroAvatar />
          </div>
        </div>
        <SkillsBar />
      </section>

      <section id="story" class="z-10">
        <SectionTitle firstTitle="Mon" secondTitle="Histoire" />
        <StorySection />
      </section>

      <section id="experience" class="z-10">
        <SectionTitle firstTitle="Mon" secondTitle="Parcours" />
        <ExperienceTimeline class="w-full max-w-5xl" />
      </section>

      <section id="projects" class="z-10">
        <SectionTitle firstTitle="Mes" secondTitle="Projets" />
        <div
          class="flex flex-col lg:flex-row gap-8 lg:gap-4 w-full max-w-7xl justify-between items-center px-8 z-10"
        >
          <ProjectCard />
        </div>
      </section>

      <BackToTop />

      <Footer />
    </main>
  </div>
</template>
