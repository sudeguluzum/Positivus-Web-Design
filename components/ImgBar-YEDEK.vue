<template>
  <div class="relative">
    <NuxtImg src="Artboard1.png" class="w-full object-cover" />
    <div class="w-full absolute top-0 left-0 flex-shrink-0 z-20 py-10">
      <div
        class="absolute inset-0 top-0 left-0 right-0 h-65 bg-gradient-to-b from-[#070B14] via-[#070B14]/80 to-transparent"
      />
      <ul class="flex space-x-6 flex-center h-8 justify-center">
        <li v-for="(i, index) in menu" :key="index" class="relative group">
          <NuxtLink
            :to="i.url"
            class="text-white flex-center flex-col px-2 py-1"
          >
            <NuxtImg :src="i.image" class="h-8" />

            <div class="flex items-center gap-1 mt-1">
              <span class="text-sm text-center">{{ i.title }}</span>
              <Icon
                v-if="i.title === 'Oyunlar'"
                name="mingcute:down-line"
                class="w-4 h-4 text-white"
              />
            </div>
          </NuxtLink>
          <div
            class="absolute bottom-0 left-0 w-full h-1 bg-gradient-to-r from-[#1b9a88] to-[#1C3E7E] opacity-0 group-hover:opacity-100 transition-all duration-300"
          ></div>
        </li>
      </ul>
    </div>

    <div class="relative z-20 h-[600px]"></div>
  </div>
</template>
<script setup>
const menu = [
  { image: "ImgBarIcons/games.png", title: "Oyunlar", url: "" },
  { image: "ImgBarIcons/gift.png", title: "Hediye Kartları", url: "" },
  { image: "ImgBarIcons/card.png", title: "Ödeme Kartları", url: "" },
  { image: "ImgBarIcons/category.png", title: "Kategoriler", url: "" },
  { image: "ImgBarIcons/invite.png", title: "Davet Et Kazan", url: "" },
  { image: "ImgBarIcons/wheel.png", title: "Ödül Çarkı", url: "" },
  { image: "ImgBarIcons/balance.png", title: "Bakiye Yükle", url: "" },
];
</script>
