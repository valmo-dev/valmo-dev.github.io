<script setup>
defineProps({
  firstTitle: {
    type: String,
    required: true,
  },
  secondTitle: {
    type: String,
    required: true,
  },
})
</script>

<template>
  <div
    class="flex flex-col w-full max-w-5xl mx-auto px-4 sm:px-0 mt-6 sm:mt-12 z-10 items-center text-center"
  >
    <h1
      class="text-4xl sm:text-6xl md:text-[80px] lg:text-8xl font-bold uppercase text-transparent custom-text-outline-white"
    >
      {{ firstTitle }}
    </h1>
    <h1
      class="text-4xl sm:text-6xl md:text-[80px] lg:text-8xl font-bold uppercase text-primary z-10 -mt-8 sm:-mt-10 md:-mt-12 text-end"
    >
      {{ secondTitle }}
    </h1>
  </div>
</template>
