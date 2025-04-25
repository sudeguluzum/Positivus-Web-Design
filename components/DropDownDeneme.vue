<template>
    <ul
      v-if="show"
      class="absolute z-10 w-full bg-white border border-gray-300 rounded-md mt-1 max-h-48 overflow-y-auto shadow-lg"
    >
      <li
        v-for="(item, index) in items"
        :key="index"
        @click="$emit('select', item)"
        class="px-4 py-2 hover:bg-purple-100 cursor-pointer flex items-center gap-2 text-black"
      >
        <Icon :name="item.icon" class="text-xl" />
        {{ item.text }}
      </li>
    </ul>
  </template>
  
  <script setup>
  defineProps([
    "items",
    "show"
  ])
  
  defineEmits(['select'])
  </script>
  