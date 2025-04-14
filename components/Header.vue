<template>
  <div class="bg-[#070B14] h-26 flex-center">
    <div
      class="max-w-[1060px] w-full px-4 flex items-center justify-between gap-1 mx-auto"
    >
      <div class="flex-wrap pt-3">
        <NuxtImg src="Logo.png" class="h-14 min-w-44" />
        <h1 class="text-white text-center">Sude Gül ÜZÜM</h1>
      </div>

      <div class="hidden md:block w-full max-w-md">
        <Searchbar />
      </div>

      <div class="flex items-center gap-3">
        <!-- Mobil hamburger menü -->
        <div class="md:hidden">
          <button @click="menuOpen = !menuOpen">
            <Icon name="mdi:menu" class="text-white w-6 h-6" />
          </button>
        </div>

        <!-- Masaüstü menü -->
        <div class="hidden md:flex">
          <ul class="flex items-center space-x-3">
            <li>
              <NuxtLink to="/" class="text-white flex items-center">
                <Icon
                  name="mdi:heart-outline"
                  class="w-5 h-5 text-green-700 mr-1"
                />
                Favorilerim
              </NuxtLink>
            </li>
            <li>
              <NuxtLink to="/" class="text-white flex items-center">
                <Icon name="openmoji:flag-turkey" class="text-2xl mr-1" />
                Türkçe
                <Icon
                  name="mingcute:down-line"
                  class="w-5 h-5 text-white ml-1"
                />
              </NuxtLink>
            </li>
            <li
              class="h-7 px-3 flex items-center text-white rounded-full bg-gradient-to-r from-[#1b9a88] to-[#1C3E7E]"
            >
              <NuxtLink to="/" class="flex items-center justify-center">
                acililahmacun
              </NuxtLink>
            </li>
          </ul>
        </div>
      </div>
    </div>

    <!-- Mobil Menü Açılır -->
    <div
      v-if="menuOpen"
      class="md:hidden absolute top-20 left-0 w-full bg-[#070B14] z-50 p-4"
    >
      <ul class="space-y-3 text-white text-center">
        <li>
          <NuxtLink to="/" class="block">Favorilerim</NuxtLink>
        </li>
        <li>
          <NuxtLink to="/" class="block">Türkçe</NuxtLink>
        </li>
        <li>
          <NuxtLink to="/" class="block">acililahmacun</NuxtLink>
        </li>
      </ul>
    </div>
  </div>
</template>

<script setup>
import { ref } from "vue";
const menuOpen = ref(false);
</script>
