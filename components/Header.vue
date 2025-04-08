<template>
  <div class="bg-[#070B14] h-20 flex-center space-x-3">
    <div class="max-w-[1200px] w-full flex justify-between items-center gap-5">
      <NuxtImg src="Logo.png" class="h-14" />

      <Searchbar />

      <div class="relative w-full ">
        <ul class="flex space-x-5 flex-center">
          <li class="flex-1 min-w-[auto]">
            <NuxtLink
              to="/fav"
              class="text-white flex items-center justify-center"
            >
              <Icon name="mdi:heart-outline" class="w-5 h-5 text-green-700 mr-1" />
              Favorilerim
            </NuxtLink>
          </li>
          <li
            class="flex-1 min-w-[95] h-7 px-2 flex-center text-white rounded-full bg-gradient-to-r from-[#1b9a88] to-[#1C3E7E]"
          >
            <NuxtLink to="/" class="flex items-center justify-center">
              acililahmacun
            </NuxtLink>
          </li>
          <li class="flex-1 min-w-[95px] h-7 px-2 text-green-700 rounded-full bg-white">
            <NuxtLink to="/" class="flex items-center justify-center">
              Satıcı Ol
            </NuxtLink>
          </li>
          <li class="flex-1 min-w-[auto]">
            <NuxtLink
              to="/fav"
              class="text-white flex items-center justify-center"
            >
              <Icon
                name="openmoji:flag-turkey"
                class="h-13"
              />
              Türkçe
              <Icon name="mingcute:down-line" class="w-5 h-5 text-white" />
            </NuxtLink>
          </li>
          <li class="flex-1 min-w-[100px]">
            <NuxtLink
              to="/contact"
              class="text-white flex items-center justify-center font-bold"
            >
              Bakiye Yükle
            </NuxtLink>
          </li>
        </ul>
      </div>
    </div>
  </div>
</template>
<script setup></script>
