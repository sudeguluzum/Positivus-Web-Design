<template>
  <div
    class="mt-5 relative bg-gradient-to-r from-[#070B14]/45 to-[#06152e]/80 z-10 rounded-3xl mx-auto h-[320px] flex-center flex-col p-4 sm:p-6 md:p-8 lg:p-10 max-w-5xl"
  >
    <div
      class="text-white font-bold mb-6 text-center text-2xl xs:text-3xl sm:text-4xl md:text-4xl"
    >
      <h2>Trend Oyunlar</h2>
    </div>
    <div class="w-full max-w-6xl">
      <div class="relative w-full">
        <TrendSliderComp :images="images" />
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
</script>
