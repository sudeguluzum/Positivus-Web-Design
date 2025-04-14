<template>
  <div class="py-10 my-10">
    <h2
      class="text-white font-bold text-center text-2xl xs:text-3xl sm:text-4xl md:text-4xl"
    >
      Yeni Ürünler
    </h2>
    <div class="mx-auto mt-8 md:max-w-5xl sm:max-w-3xl">
      <ClientOnly>
        <Carousel
          :items-to-show="8"
          :wrap-around="true"
          :autoplay="2000"
          :transition="1000"
          :mouse-drag="true"
          :pause-autoplay-on-hover="false"
          :slide-gap="0" 
          
          :breakpoints="{
            1024: { itemsToShow: 8 },
            768: { itemsToShow: 7 },
            640: { itemsToShow: 6 },
            0: { itemsToShow: 3 },
          }"
          
        >
          <Slide
            v-for="(i, index) in products"
            :key="index"
            v-slot="{ isActive }"
            ><NewProductsComp
              :image="i.image"
              :title="i.subtitle"
              :is-active="isActive"
            />
          </Slide>
        </Carousel>
      </ClientOnly>
    </div>

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

<style scoped>

</style>
