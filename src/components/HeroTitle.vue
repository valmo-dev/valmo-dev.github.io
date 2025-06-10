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
  <div class="flex flex-col w-full max-w-5xl mx-auto px-4 sm:px-0 mt-6 sm:mt-8">
    <h1
      class="text-4xl sm:text-6xl md:text-[80px] lg:text-8xl font-bold uppercase text-primary z-20 ml-4 sm:ml-8 md:ml-12"
    >
      {{ firstTitle }}
    </h1>
    <h1
      class="text-4xl sm:text-6xl md:text-[80px] lg:text-8xl font-bold uppercase text-transparent custom-text-outline-white self-end -mt-6 sm:-mt-8 md:-mt-10 mr-4 sm:mr-8 md:mr-12 z-10"
    >
      {{ secondTitle }}
    </h1>
  </div>
</template>
