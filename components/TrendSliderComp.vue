<template>
  <div class="bg-pink-300 h-60 mt-8 md:max-w-5xl sm:max-w-3xl">
    <ClientOnly>
      <Carousel :items-to-show="5" class="mx-10">
        <Slide v-for="(i, index) in images" :key="index" class="px-2">
         
        </Slide>
        <template #addons>
          <Navigation />
        </template>
      </Carousel>
    </ClientOnly>
  </div>
</template>

<script setup>
  const images = [
    { image: "trend_oyun1.png", title: "Free Fire" },
    { image: "trend_oyun2.png", title: "Playstation Gift Card" },
    { image: "trend_oyun3.png", title: "XBOX Gift Card" },
    { image: "trend_oyun4.png", title: "Apex Legends" },
    { image: "trend_oyun5.png", title: "Rainbow Six Siege" },
    { image: "trend_oyun6.png", title: "Oyun 6" },
    { image: "trend_oyun7.png", title: "Oyun 7" },
    { image: "trend_oyun8.png", title: "Oyun 8" },
    { image: "trend_oyun9.png", title: "Oyun 9" },
    { image: "trend_oyun10.png", title: "Oyun 10" },
  ];
</script>
