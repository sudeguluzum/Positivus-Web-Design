<template>
  <div
    class="flex flex-col items-center gap-3 mx-4 md:flex-row md:gap-10 md:justify-start my-20"
  >
    <h1 class="c-green p-1 font-semibold text-3xl flex-center w-fit">
      {{ title }}
    </h1>
    <p v-html="text" class="text-black text-sm md:text-md"></p>
  </div>
</template>

<script setup>
const props = defineProps({ title: String, text: String });
</script>
