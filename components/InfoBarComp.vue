<template>
  <div class="flex-center gap-1.5 text-center text-white">
    <NuxtImg :src="image" class="w-24" />
    <div>
      <p class="my-2 font-semibold">{{ title }}</p>
      <p class="max-w-48 text-balance text-sm">
        {{ info }}
      </p>
    </div>
  </div>
</template>

<script setup>
defineProps(["image", "title", "info"]);
</script>
