<template>
 
    <div
      class="rounded-full h-16 w-16 flex-center"
    >
      <NuxtImg :src="image" class="h-16 w-16" />
    </div>
 
</template>

<script setup>
defineProps(["image"]);
</script>
