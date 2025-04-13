<template>
  <NuxtLink
    class="h-32 w-32 relative transition-all z-0 block"
    :to="url"
    :class="[isActive ? 'scale-100 z-10' : 'scale-80 opacity-60']"
  >
    <NuxtImg
      :src="image"
      class="w-32 h-32 transition-all duration-300"
      :class="[isActive ? 'grayscale-0' : 'grayscale']"
    />
    <div
      class="flex justify-center items-center absolute w-full h-full top-0 left-0 bg-gradient-to-r from-[#1b9a88]/50 to-[#1C3E7E]/50"
      :class="isActive ? 'opacity-100' : 'opacity-0'"
    >
      <p class="text-center font-bold text-balance text-white">
        {{ title }}
      </p>
    </div>
  </NuxtLink>
</template>

<script setup>
defineProps(["image", "title", "url", "isActive"]);
</script>

<style>
.group:hover {
  z-index: 20;
}
</style>

<!-- <template>
  <NuxtLink
    class="h-32 w-32 relative group transition-all z-0 hover:z-5 hover:scale-120"
    :to="url"
  >
    <NuxtImg :src="image" class="w-32 h-32" />
    <div
      class="flex justify-center items-center absolute w-full h-full transition-all duration-300 top-0 left-0 bg-gradient-to-r from-[#1b9a88]/50 to-[#1C3E7E]/50 opacity-0 group-hover:opacity-100"
    >
      <p class="text-center font-bold text-balance text-white">{{ title }}</p>
    </div>
  </NuxtLink>
</template>

<script setup>
defineProps(["image", "title", "url"]);
</script>

<style>
.group:hover {
  z-index: 20;
}
</style> -->

<!-- <template>
  <ClientOnly>
    <Carousel :wrap-around="true">
      <Slide>
        <NuxtLink
          class="h-32 w-32 relative group transition-all z-0 hover:z-5 hover:scale-120"
          :to="url"
        >
          <NuxtImg :src="image" class="w-32 h-32 grayscale hover:grayscale-0" />
          <div
            class="flex justify-center items-center absolute w-full h-full transition-all duration-300 top-0 left-0"
          >
            <p class="text-center font-bold text-balance text-white">
              {{ title }}
            </p>
          </div>
        </NuxtLink>
      </Slide>
    </Carousel>
  </ClientOnly>
</template>
<script setup>
defineProps(["image", "title", "url"]);
</script> -->
