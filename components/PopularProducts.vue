<template>
  <div class="bg-gray-700 relative h-75 mt-8">
    <div
      class="absolute text-white text-4xl font-bold mb-4 text-center left-1/2 transform -translate-x-1/2"
    >
      <h1>Popüler Ürünler</h1>
    </div>

    <div
      class="h-50 w-[52%] absolute left-1/2 transform -translate-x-1/2 top-10 flex-center flex-wrap"
    >
    <PopularProductsComp v-for="(i,index) in products" :image="i.image" :subtitle="i.subtitle" />


</div>
  </div>
</template>
<script setup>
const products = [
  { image: "popular-product1.png",subtitle:"11950 UC GLOBAL"},
  { image: "popular-product1.png",subtitle:"11950 UC GLOBAL"},
  { image: "popular-product1.png",subtitle:"11950 UC GLOBAL"},
  { image: "popular-product1.png",subtitle:"11950 UC GLOBAL"},
  { image: "popular-product1.png",subtitle:"11950 UC GLOBAL"},
  { image: "popular-product1.png",subtitle:"11950 UC GLOBAL"},
  { image: "popular-product1.png",subtitle:"11950 UC GLOBAL"},
  { image: "popular-product1.png",subtitle:"11950 UC GLOBAL"},

];
</script>
