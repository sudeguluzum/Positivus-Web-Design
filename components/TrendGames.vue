<template>
  <div
    class="relative bg-gradient-to-r from-[#070B14]/45 to-[#06152e]/80 z-10 rounded-3xl mx-auto h-[320px] flex-center flex-col p-4 sm:p-6 md:p-8 lg:p-10 max-w-5xl"
  >
    <div
      class="text-white font-bold mb-6 text-center text-2xl xs:text-3xl sm:text-4xl md:text-4xl"
    >
      <h2>Trend Oyunlar</h2>
    </div>
    <div class="w-full max-w-6xl">
      <div class="relative w-full">
        <div
          ref="scrollContainer"
          class="mx-20 flex overflow-x-auto scroll-smooth scrollbar-hide px-3 space-x-4"
          style="scroll-snap-type: x mandatory"
        >
          <TrendGamesComp
            v-for="(i, index) in images"
            :image="i.image"
            :title="i.title"
          />
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
  { image: "trendGames/trend_oyun1.png", title: "Free Fire" },
  { image: "trendGames/trend_oyun2.png", title: "Playstation Gift Card" },
  { image: "trendGames/trend_oyun3.png", title: "XBOX Gift Card" },
  { image: "trendGames/trend_oyun4.png", title: "Apex Legends" },
  { image: "trendGames/trend_oyun5.png", title: "Rainbow Six Siege" },
  { image: "trendGames/trend_oyun6.png", title: "Oyun 6" },
  { image: "trendGames/trend_oyun7.png", title: "Oyun 7" },
  { image: "trendGames/trend_oyun8.png", title: "Oyun 8" },
  { image: "trendGames/trend_oyun9.png", title: "Oyun 9" },
  { image: "trendGames/trend_oyun10.png", title: "Oyun 10" },
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
