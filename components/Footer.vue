<template>
  <footer class="py-10 px-6 text-sm text-gray-700 leading-none bg-white">
    <div
      class="max-w-7xl mx-auto grid grid-cols-2 md:grid-cols-5 gap-24"
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
            <NuxtLink to="/contact"> Anında Canlı Destek </NuxtLink>
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
</template>

<script setup>
const footerColumns = [
  {
    title: "Egin Pay",
    items: [
      { text: "Hakkımızda", link: "/about" },
      { text: "Kariyer", link: "/careers" },
      { text: "Kurumsal", link: "/corporate" },
      { text: "Kurumsal Kimlik", link: "/branding" },
      { text: "Favorilerim", link: "/favorites" },
      { text: "Haberler", link: "/news" },
      { text: "İletişim", link: "/contact" },
    ],
  },
  {
    title: "Kullanıcı",
    items: [
      { text: "Kayıt Ol", link: "/register" },
      { text: "Şifremi Unuttum", link: "/forgot-password" },
      { text: "Mağaza", link: "/store" },
      { text: "Yayıncı Başvurusu", link: "/publisher-application" },
      { text: "Ödeme Yöntemleri", link: "/payment-methods" },
      { text: "Kullanıcı Sözleşmesi", link: "/terms" },
      { text: "KVKK", link: "/kvkk" },
      { text: "Çerez Politikası", link: "/cookie-policy" },
      { text: "Gizlilik Sözleşmesi", link: "/privacy" },
      { text: "Rıza Metni", link: "/consent" },
    ],
  },
  {
    title: "Oyuncu Pazarı",
    items: [
      { text: "PUBG Mobile", link: "/games/pubg-mobile" },
      { text: "PUBG Mobile New State", link: "/games/pubg-new-state" },
      { text: "Metin 2", link: "/games/metin2" },
      { text: "Knight Online", link: "/games/knight-online" },
      { text: "CS:GO", link: "/games/csgo" },
      { text: "Steam", link: "/games/steam" },
      { text: "Point Blank", link: "/games/point-blank" },
      { text: "Minecraft", link: "/games/minecraft" },
      { text: "İlan Rütbe Sistemi", link: "/ranking-system" },
    ],
  },
  {
    title: "Popüler Sayfalar",
    items: [
      { text: "Metin2", link: "/popular/metin2" },
      { text: "PUBG Mobile", link: "/popular/pubg-mobile" },
      { text: "PUBG Mobile Lite", link: "/popular/pubg-mobile-lite" },
      { text: "Valorant", link: "/popular/valorant" },
      { text: "League Of Legends", link: "/popular/lol" },
      { text: "Steam", link: "/popular/steam" },
      { text: "Cabal Online", link: "/popular/cabal" },
      { text: "Mobile Legends", link: "/popular/mobile-legends" },
      { text: "Zula", link: "/popular/zula" },
      { text: "Knight Online", link: "/popular/knight-online" },
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
