<template>
  <div
    class="w-[140px] h-[220px] flex-shrink-0 flex flex-col items-center cursor-pointer hover:scale-105 transition-transform duration-300"
  >
    <NuxtImg
      :src="image"
      class="w-full h-[180px] object-contain rounded-xl"
      :alt="title"
    />
    <div class="text-center mt-2 text-sm font-semibold text-white">
      {{ title }}
    </div>
  </div>
</template>

<script setup>
const props = defineProps(["image", "title"]);
</script>
