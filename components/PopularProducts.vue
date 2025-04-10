<template>
  <div class="py-10 bg-gray-700 my-10">
    <h2
      class="text-white font-bold  text-center text-2xl xs:text-3xl sm:text-4xl md:text-4xl"
    >
      Popüler Ürünler
    </h2>

    <div class="flex-center flex-wrap max-md:gap-y-5 mt-5">
      <PopularProductsComp
        v-for="(i, index) in products"
        :image="i.image"
        :title="i.subtitle"
      />
    </div>
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
