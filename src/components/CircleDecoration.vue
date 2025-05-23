<script setup>
defineProps({
  color: {
    type: String,
    required: true,
  },
})
</script>

<template>
  <div
    class="w-[500px] h-[500px] sm:w-[650px] sm:h-[650px] md:w-[883px] md:h-[883px] rounded-full opacity-50 md:opacity-100"
    :class="[`bg-${color}`]"
  ></div>
</template>
