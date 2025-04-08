<template>
    <div class=" group relative h-30 w-30" style="z-index: auto;">
    
      <NuxtImg 
        :src="image"
        class="h-full w-full object-cover transition-all duration-300 transform hover:z-30 hover:scale-120 hover:shadow-xl"
        style="position: relative;"
      />
      
 
      <div class="absolute w-[calc(100%*1.2)] left-1/2 -translate-x-1/2 h-7 top-full left-0 right-0 mt-5 bg-white text-black text-sm px-1 py-1 rounded-b-md 
                  opacity-0 group-hover:opacity-100 transition-opacity duration-300 text-center font-semibold">
        {{ subtitle }}
      </div>
    </div>
  </template>
  
  <script setup>
  defineProps(["image", "subtitle"]);
  </script>
  
  <style>
  .group:hover {
    z-index: 20;
  }
  </style>