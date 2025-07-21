<template>
  <div
    class="c-black grid grid-cols-1 md:grid-cols-3 divide-y md:divide-y-0 md:divide-x-1 divide-gray-500 p-4 text-white rounded-4xl my-20"
  >
    <div v-for="(i, j) in cases" :key="j" class="p-10">
      <p class="leading-relaxed">
        {{ i.text }}
      </p>
      <NuxtLink
        :to="i.url"
        class="text-green inline-flex items-center gap-1 hover:scale-101 pt-5"
      >
        Learn more
        <NuxtImg src="anasayfa/index-card/green-ok.png" class="w-7" />
      </NuxtLink>
    </div>
  </div>
</template>

<script setup>
const props = defineProps({
  cases: {
    type: Array,
    required: true,
    default: () => [],
  },
});
</script>
