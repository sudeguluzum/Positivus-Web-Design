<template>
  <div
    class=" p-12 bg-gradient-to-r from-[#1b9a88]/70 to-[#1C3E7E]/70 w-full flex-center gap-14 flex-wrap"
  >
    <InfoBarComp
      v-for="(i, j) in logo"
      :key="j"
      :image="i.image"
      :title="i.title"
      :info="i.info"
    />
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
