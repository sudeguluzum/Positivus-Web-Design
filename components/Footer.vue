<template>
  <div class="bg-[#252627] bg-[url(/bg-img/WebBG.png)]">
    <Infobar />
  </div>
  <EBulletin />

  <footer class="py-10 px-6 text-sm text-gray-700 leading-none">
    <div class="max-w-7xl mx-auto h-20 flex items-center gap-2">
      <p class="text-sm">Payment methods:</p>
      <div
        v-for="(i, index) in images"
        :key="index"
        class="flex justify-center items-center"
      >
        <NuxtImg :src="i.image" class="h-6" />
      </div>
    </div>

    <div
      class="max-w-7xl mx-auto grid grid-cols-1 sm:grid-cols-2 md:grid-cols-5 gap-10"
    >
      <div v-for="(column, index) in footerColumns" :key="index">
        <h3 class="text-[#1b9a88] font-semibold mb-2">{{ column.title }}</h3>
        <ul class="space-y-1">
          <li v-for="(item, itemIndex) in column.items" :key="itemIndex">
            <NuxtLink v-if="item.link" :to="item.link">
              {{ item.text }}
            </NuxtLink>
            <template v-else>
              {{ item.text }}
            </template>
          </li>
        </ul>
      </div>

      <div>
        <h3
          class="bg-gradient-to-r from-[#1b9a88] to-[#1C3E7E] bg-clip-text text-transparent font-semibold mb-2"
        >
          Bize Geri Bildirim Bırak
        </h3>
        <ul class="space-y-1 mb-6">
          <li>
            <NuxtLink to="/"> Anında Canlı Destek </NuxtLink>
          </li>
          <li>
            <a href="mailto:destek@epinpay.com"> destek@epinpay.com </a>
          </li>
        </ul>

        <h3
          class="font-bold bg-gradient-to-r from-[#1b9a88] to-[#1C3E7E] bg-clip-text text-transparent mb-2"
        >
          Sosyal Medya Hesaplarımız
        </h3>
        <div class="flex gap-2 mt-4">
          <NuxtLink
            v-for="(social, index) in socialIcons"
            :key="index"
            :to="social.url"
            target="_blank"
            external
            class="w-8 aspect-square rounded-full flex items-center justify-center bg-gradient-to-r from-[#1b9a88] to-[#1C3E7E]"
          >
            <Icon :name="social.icon" class="text-[24px] text-white" />
          </NuxtLink>
        </div>
      </div>
    </div>
    
  </footer>
  <div class="w-full h-0.5 bg-gradient-to-r from-[#1b9a88] to-[#1C3E7E]"></div>
  <div class="py-6 text-center text-sm sm:text-base">
    <div class="flex-center flex-col space-y-2 text-gray-700">
      <NuxtImg src="footer-logo.svg" class="h-6 sm:h-8" />
      <p class="font-semibold text-black">MEGATRON TECHNOLOGY LTD.</p>

      <p class="text-black">
        Yardım Merkezi: support@epinpay.com 10:00 - 17:00
      </p>
    </div>
  </div>
</template>

<script setup>
const images = [
  { image: "payment1.png" },
  { image: "payment2.png" },
  { image: "payment3.png" },
  { image: "payment4.svg" },
];
const footerColumns = [
  {
    title: "Epin Pay",
    items: [
      { text: "Hakkımızda", link: "/" },
      { text: "Kariyer", link: "/" },
      { text: "Kurumsal", link: "/" },
      { text: "Kurumsal Kimlik", link: "/" },
      { text: "Favorilerim", link: "/" },
      { text: "Haberler", link: "/" },
      { text: "İletişim", link: "/" },
    ],
  },
  {
    title: "Kullanıcı",
    items: [
      { text: "Kayıt Ol", link: "/" },
      { text: "Şifremi Unuttum", link: "/" },
      { text: "Mağaza", link: "/" },
      { text: "Yayıncı Başvurusu", link: "/" },
      { text: "Ödeme Yöntemleri", link: "/" },
      { text: "Kullanıcı Sözleşmesi", link: "/" },
      { text: "KVKK", link: "/" },
      { text: "Çerez Politikası", link: "/" },
      { text: "Gizlilik Sözleşmesi", link: "/" },
      { text: "Rıza Metni", link: "/" },
    ],
  },
  {
    title: "Oyuncu Pazarı",
    items: [
      { text: "PUBG Mobile", link: "/" },
      { text: "PUBG Mobile New State", link: "/" },
      { text: "Metin 2", link: "/" },
      { text: "Knight Online", link: "/" },
      { text: "CS:GO", link: "/" },
      { text: "Steam", link: "/" },
      { text: "Point Blank", link: "/" },
      { text: "Minecraft", link: "/" },
      { text: "İlan Rütbe Sistemi", link: "" },
    ],
  },
  {
    title: "Popüler Sayfalar",
    items: [
      { text: "Metin2", link: "/" },
      { text: "PUBG Mobile", link: "/" },
      { text: "PUBG Mobile Lite", link: "/" },
      { text: "Valorant", link: "/" },
      { text: "League Of Legends", link: "/" },
      { text: "Steam", link: "/" },
      { text: "Cabal Online", link: "/" },
      { text: "Mobile Legends", link: "/" },
      { text: "Zula", link: "/" },
      { text: "Knight Online", link: "/" },
    ],
  },
];

// Sosyal medya ikonları
const socialIcons = [
  { icon: "ic:baseline-facebook", url: "https://facebook.com/" },
  { icon: "uim:instagram", url: "https://instagram.com/" },
  { icon: "mdi:youtube", url: "https://youtube.com/" },
  { icon: "ic:baseline-tiktok", url: "https://tiktok.com/" },
  { icon: "mdi:twitch", url: "https://twitch.tv/" },
];
</script>
