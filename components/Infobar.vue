<template>
  <div
    class="mt-20 p-12 bg-gradient-to-r from-[#1b9a88] to-[#1C3E7E] w-full flex-center gap-14 flex-wrap"
  >
    <div
      class="flex-center gap-1.5 text-center text-white"
      v-for="(i, j) in logo"
      :key="j"
    >
      <NuxtImg :src="i.image" class="h-26" />
      <div>
        <p class="my-2 font-semibold">{{ i.title }}</p>
        <p class="max-w-48 text-balance text-sm">
          {{ i.info }}
        </p>
      </div>
    </div>
  </div>
</template>

<script setup>
const logo = [
  {
    image: "/footer-icons/rocket.svg",
    title: "Hızlı Teslimat",
    info: "Aldığınız kod anında hesabınızda! 7/24 teslimat.",
  },
  {
    image: "/footer-icons/shield.svg",
    title: "Güvenli Alışveriş",
    info: "3D Secure ve SSL güvencesiyle dilediğiniz ödeme yöntemi ile ödeme yapın.",
  },
  {
    image: "/footer-icons/percent.svg",
    title: "En Uygun Fiyatlar",
    info: "İndirimli ve ucuz fiyatlarla alışverişin keyfini çıkarın.",
  },
  {
    image: "/footer-icons/smile.svg",
    title: "Müşteri Memnuniyeti ",
    info: "Oyun alışverişinizde bizi tercih ettiğiniz için teşekkür ederiz.",
  },
];
</script>
