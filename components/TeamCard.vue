<template>
  <div
    class="flex flex-col gap-5 border p-5 md:p-10 rounded-4xl border-b-6 hover:shadow-xl hover:shadow-gray-800 hover:scale-101"
  >
    <div class="flex justify-between">
      <NuxtImg :src="img" class="w-20 h-20" />
      <span class="flex flex-col justify-end">
        <h1 class="font-semibold text-xl">{{ name }}</h1>
        <h2 class="text-lg">{{ departman }}</h2>
      </span>
      <div class="relative rounded-full c-green w-6 h-6 flex-center">
        <Icon
          name="entypo-social:linkedin-with-circle"
          class="absolute text-3xl"
        />
      </div>
    </div>

    <div class="pt-5 border-t-1">
      <p>{{ info }}</p>
    </div>
  </div>
</template>

<script setup>
const props = defineProps({
  img: String,
  name: String,
  departman: String,
  info: String,
});
</script>
