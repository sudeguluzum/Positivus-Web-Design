<template>
    <div class="h-60  flex-center flex-wrap gap-2">
      <GameDivComp
        v-for="(i, index) in images"
        :key="index"
        :image="i.image"
        
      >
      </GameDivComp>
    </div>
  </template>
  <script setup>
  
  const images = [
    { image: '/oyunlarYuvarlak/logo1.png' },
    { image: '/oyunlarYuvarlak/logo2.png' },
    { image: '/oyunlarYuvarlak/logo3.png' },
    { image: '/oyunlarYuvarlak/logo4.png' },
    { image: '/oyunlarYuvarlak/logo5.png' },
    { image: '/oyunlarYuvarlak/logo6.png' },
    { image: '/oyunlarYuvarlak/logo7.png' },
    { image: '/oyunlarYuvarlak/logo8.png' },
    { image: '/oyunlarYuvarlak/logo9.png' },
    { image: '/oyunlarYuvarlak/logo10.png' },
    { image: '/oyunlarYuvarlak/logo11.png' },
    { image: '/oyunlarYuvarlak/logo12.png' },
    { image: '/oyunlarYuvarlak/logo13.png' },
    { image: '/oyunlarYuvarlak/logo14.png' },

  ];
</script>
