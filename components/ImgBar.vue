<template>
  <div class="relative">
    <div class="absolute inset-0 z-0">
      <NuxtImg src="Artboard1.png" class="w-full h-full object-cover" />
    </div>

    <div
      class="absolute inset-0 bg-gradient-to-b from-[#070B14] via-[#070B14]/80 to-transparent z-10"
    ></div>

    <div class="relative z-20 py-10">
      <ul class="flex space-x-6 flex-center h-8 justify-center">
        <li class="relative group">
          <NuxtLink
            to="/"
            class="text-white flex items-center justify-center px-2 py-1"
          >
            Oyunlar
            <Icon name="mingcute:down-line" class="w-5 h-5 text-white" />
          </NuxtLink>
          <div
            class="absolute bottom-0 left-0 w-full h-1 bg-gradient-to-r from-[#1b9a88] to-[#1C3E7E] opacity-0 group-hover:opacity-100 transition-all duration-300"
          ></div>
        </li>
        <li class="relative group">
          <NuxtLink
            to="/"
            class="text-white flex items-center justify-center px-2 py-1"
          >
            Hediye Kartları
          </NuxtLink>
          <div
            class="absolute bottom-0 left-0 w-full h-1 bg-gradient-to-r from-[#1b9a88] to-[#1C3E7E] opacity-0 group-hover:opacity-100 transition-all duration-300"
          ></div>
        </li>

        <li class="relative group">
          <NuxtLink
            to="/"
            class="text-white flex items-center justify-center px-2 py-1"
          >
            Ödeme Kartları
          </NuxtLink>
          <div
            class="absolute bottom-0 left-0 w-full h-1 bg-gradient-to-r from-[#1b9a88] to-[#1C3E7E] opacity-0 group-hover:opacity-100 transition-all duration-300"
          ></div>
        </li>

        <li class="relative group">
          <NuxtLink
            to="/"
            class="text-white flex items-center justify-center px-2 py-1"
          >
            Kategoriler
          </NuxtLink>
          <div
            class="absolute bottom-0 left-0 w-full h-1 bg-gradient-to-r from-[#1b9a88] to-[#1C3E7E] opacity-0 group-hover:opacity-100 transition-all duration-300"
          ></div>
        </li>

        <li class="relative group">
          <NuxtLink
            to="/"
            class="text-white flex items-center justify-center px-2 py-1"
          >
            Davet Et Kazan
          </NuxtLink>
          <div
            class="absolute bottom-0 left-0 w-full h-1 bg-gradient-to-r from-[#1b9a88] to-[#1C3E7E] opacity-0 group-hover:opacity-100 transition-all duration-300"
          ></div>
        </li>

        <li class="relative group">
          <NuxtLink
            to="/"
            class="text-white flex items-center justify-center px-2 py-1"
          >
            Ödül Çarkı
          </NuxtLink>
          <div
            class="absolute bottom-0 left-0 w-full h-1 bg-gradient-to-r from-[#1b9a88] to-[#1C3E7E] opacity-0 group-hover:opacity-100 transition-all duration-300"
          ></div>
        </li>

        <li class="relative group">
          <NuxtLink
            to="/"
            class="text-white flex items-center justify-center px-2 py-1"
          >
            Bakiye Yükle
          </NuxtLink>
          <div
            class="absolute bottom-0 left-0 w-full h-1 bg-gradient-to-r from-[#1b9a88] to-[#1C3E7E] opacity-0 group-hover:opacity-100 transition-all duration-300"
          ></div>
        </li>
      </ul>
    </div>

    <div class="relative z-20 h-[600px]">
    
    </div>
  </div>
</template>