<template>
  <div class="py-10 bg-gray-700 my-10">
    <h2
      class="text-white font-bold text-center text-2xl xs:text-3xl sm:text-4xl md:text-4xl"
    >
      Popüler Ürünler
    </h2>

    <ClientOnly>
      <Carousel
        :items-to-show="8"
        :wrap-around="true"
        :autoplay="2000"
        :transition="1000"
        :mouse-drag="true"
        :pause-autoplay-on-hover="false"
        class="mt-10"
        :breakpoints="{
          1024: { itemsToShow: 4 },
          768: { itemsToShow: 3 },
          640: { itemsToShow: 2 },
          0: { itemsToShow: 1 },
        }"
      >
        <Slide
          v-for="(i, index) in products"
          :key="index"
          v-slot="{ isActive }"
          class="bg-green-200"
          ><PopularProductsComp
            :image="i.image"
            :title="i.subtitle"
            :is-active="isActive"
          />
        </Slide>
      </Carousel>
    </ClientOnly>

    <!-- <div class="flex-center flex-wrap max-md:gap-y-5 mt-5">
      <PopularProductsComp :image="i.image" :title="i.subtitle" />
    </div> -->
  </div>
</template>
<script setup>
const products = [
  { image: "popular-product1.png", subtitle: "11950 UC GLOBAL" },
  { image: "popular-product1.png", subtitle: "11950 UC GLOBAL" },
  { image: "popular-product1.png", subtitle: "11950 UC GLOBAL" },
  { image: "popular-product1.png", subtitle: "11950 UC GLOBAL" },
  { image: "popular-product1.png", subtitle: "11950 UC GLOBAL" },
  { image: "popular-product1.png", subtitle: "11950 UC GLOBAL" },
  { image: "popular-product1.png", subtitle: "11950 UC GLOBAL" },
  { image: "popular-product1.png", subtitle: "11950 UC GLOBAL" },
];
</script>
