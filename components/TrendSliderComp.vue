<template>
  <ClientOnly>
  <Carousel :wrap-around="true"  :breakpoints="{
            1280: { itemsToShow: 5 },
            1024: { itemsToShow: 5 },
            768: { itemsToShow: 4 },
            640: { itemsToShow: 4 },
            480: { itemsToShow: 2 },
            300: { itemsToShow: 1 },
          }" class="px-10">
    <Slide
      v-for="(item, index) in images"
      :key="index"
    >
      <TrendsComp :image="item.image" :title="item.title" />
    </Slide>


    <template #addons>
      <Navigation />
    </template>
  </Carousel>
</ClientOnly>
</template>

<script setup>
const props = defineProps(["images"]);
</script>

<style scoped>

::v-deep(.carousel__prev),
::v-deep(.carousel__next) {
  color: white;
}
</style>

