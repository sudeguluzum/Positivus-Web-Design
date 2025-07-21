<template>
  <div
    class="c-black grid grid-cols-1 md:grid-cols-3 divide-x-4 text-white p-10 rounded-4xl my-20"
  >
    <div>
      <p class="text-white">
        {{ text }}
      </p>
    </div>
  </div>
</template>

<script setup>
const props = defineProps({
  text: String,
  url: String,
});
</script>
