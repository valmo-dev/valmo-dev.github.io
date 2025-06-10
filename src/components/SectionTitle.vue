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
    class="flex flex-col w-full max-w-5xl mx-auto px-4 sm:px-0 my-6 sm:my-12 items-center text-center"
  >
    <h1
      class="text-4xl sm:text-6xl md:text-[80px] lg:text-8xl font-bold uppercase text-transparent custom-text-outline-white z-10"
    >
      {{ firstTitle }}
    </h1>
    <h1
      class="text-4xl sm:text-6xl md:text-[80px] lg:text-8xl font-bold uppercase text-primary -mt-6 sm:-mt-8 md:-mt-12 text-end z-20"
    >
      {{ secondTitle }}
    </h1>
  </div>
</template>
