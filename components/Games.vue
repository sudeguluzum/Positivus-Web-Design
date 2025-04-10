<template>
    <div class="h-60  flex-center flex-wrap gap-2">
      <div
        v-for="(i, index) in images"
        :key="index"
        class="rounded-full h-16 w-16 flex-center"
      >
        <NuxtImg :src="i.image" class="h-16 w-16 " />
      </div>
    </div>
  </template>
  <script setup>
  
  const images = [
    { image: 'logo1.png' },
    { image: 'logo2.png' },
    { image: 'logo3.png' },
    { image: 'logo4.png' },
    { image: 'logo5.png' },
    { image: 'logo6.png' },
    { image: 'logo7.png' },
    { image: 'logo8.png' },
    { image: 'logo9.png' },
    { image: 'logo10.png' },
    { image: 'logo11.png' },
    { image: 'logo12.png' },
    { image: 'logo13.png' },
    { image: 'logo14.png' },

  ];
</script>
