<template>
  <div
    class="flex items-center justify-between w-full max-w-screen-xl px-4 md:mx-auto my-10"
  >
    <NuxtImg src="blackLogo.png" class="h-6 md:h-9" />
    <div class="hidden lg:flex gap-8">
      <button
        v-for="(i, j) in menu"
        :class="['', i.id === 1 ? 'border rounded-xl px-6 py-3' : 'text']"
      >
        {{ i.name }}
      </button>
    </div>
  </div>
</template>
<script setup>
const menu = [
  { name: "About us" },
  { name: "Services" },
  { name: "Use Cases" },
  { name: "Pricing" },
  { name: "Blog" },
  { name: "Request a quote", id: 1 },
];
</script>
