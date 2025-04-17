<template>
  <div>
    <NuxtLink :to="url">
      <div class="flex items-center justify-between px-4">
        <div class="flex flex-col">
          <span class="text-sm" :class="{ 'font-bold': id === 1 }">{{
            name
          }}</span>

          <span v-if="id === 1" class="text-sm text-center text-gray-900">
            Account ID: {{ AccountId }}</span
          >
        </div>
        <div class="flex-center">
          <span class="text-sm font-bold px-2">{{ point }}</span>
          <Icon v-if="icon" :name="icon" class="text-2xl text-black" />
          <NuxtImg :src="img" class="h-5" />
        </div>
      </div>
    </NuxtLink>
  </div>
</template>

<script setup>
defineProps(["id", "name", "AccountId", "url", "img", "point", "icon"]);
</script>
