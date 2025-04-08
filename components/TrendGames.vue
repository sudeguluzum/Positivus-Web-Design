<template>
  <div
    class="relative bg-[#070B14]/80 z-10 rounded-3xl w-[52%] mx-auto h-[320px] flex flex-col justify-center items-center p-6"
  >
    <div class="text-white text-4xl font-bold mb-4">
      <h1>Trend Oyunlar</h1>
    </div>
    <div class="w-full max-w-6xl">
      <div class="relative w-full">

        <div
          ref="scrollContainer"
          class="mx-20 flex overflow-x-auto scroll-smooth scrollbar-hide px-10 space-x-4"
          style="scroll-snap-type: x mandatory"
        >

        <TrendGamesComp  v-for="(i, index) in images" :image="i.image" :title="i.title"/>
          
        </div>

        <button
          @click="scrollLeft"
          class="absolute left-0 top-1/2 transform -translate-y-1/2 text-2xl text-white p-2 rounded-full z-10"
        >
          <Icon name="ooui:next-rtl" class="w-5 h-5" />
        </button>
        <button
          @click="scrollRight"
          class="absolute right-2 top-1/2 transform -translate-y-1/2 text-2xl text-white p-2 rounded-full z-10"
        >
          <Icon name="ooui:next-ltr" class="w-5 h-5" />
        </button>
      </div>
    </div>
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

const scrollContainer = ref(null);

const scrollLeft = () => {
  if (scrollContainer.value) {
    scrollContainer.value.scrollBy({ left: -700, behavior: "smooth" }); // 5 kart kadar kaydır
  }
};

const scrollRight = () => {
  if (scrollContainer.value) {
    scrollContainer.value.scrollBy({ left: 700, behavior: "smooth" });
  }
};
</script>

<style scoped>
.scrollbar-hide::-webkit-scrollbar {
  display: none;
}
.scrollbar-hide {
  -ms-overflow-style: none;
  scrollbar-width: none;
}
</style>