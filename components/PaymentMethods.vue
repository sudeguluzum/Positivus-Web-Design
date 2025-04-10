<template>
<div class="max-w-7xl mx-auto h-20 flex items-center gap-2 ">
<p class="text-sm">Payment methods:</p>
    <div
      v-for="(i, index) in images"
      :key="index"
      class="flex justify-center items-center"
    >
      <NuxtImg :src="i.image" class="h-6 " />
    </div>
</div>
</template>


<script setup>

const images = [
  { image: 'payment1.png' },
  { image: 'payment2.png' },
  { image: 'payment3.png' },
  { image: 'payment4.svg' },
 

];
</script>