<template>
  <div class="flex items-center gap-3">
    <!-- Mobil search ve hamburger menü -->
    <div class="md:hidden flex flex-wrap gap-2">
      <button
        ref="searchButton"
        @click.stop="toggleSearch"
        class="w-9 h-9 mb-1.5 flex-center text-white"
      >
        <Icon name="material-symbols:search" class="text-xl" />
      </button>
      <button @click="menuOpen = !menuOpen">
        <Icon name="mdi:menu" class="text-white text-2xl" />
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
            <Icon name="openmoji:flag-turkey" class="text-2xl mr-1" /> Türkçe
            <Icon name="mingcute:down-line" class="w-5 h-5 text-white ml-1" />
          </NuxtLink>
        </li>

        <li
          class="relative h-7 px-3 flex items-center text-white rounded-full bg-gradient-to-r from-[#1b9a88] to-[#1C3E7E]"
        >
          <NuxtLink
            to="/"
            class="flex-center"
            ref="target"
            @click="show = !show"
          >
            acililahmacun
          </NuxtLink>
          <div
            v-if="show"
            class="absolute top-full right-0 w-80 z-60 bg-white/60 backdrop-blur-md text-black text-sm rounded-b-3xl mt-2"
          >
         
            <HeaderDropDownMenuComp
            class="border-t border-gray-300 py-4"
              v-for="(i, index) in menu"
              :key="index"
              :id="i.id"
              :name="i.name"
              :point="i.point"
              :AccountId="i.AccountId"
              :url="i.url"
              :img="i.img"
              :icon="i.icon"
            />
          </div>
        </li>
      </ul> 
    </div>
  </div>
  <!-- Mobil Menü Açılır -->
  <div
    v-if="menuOpen"
    class="md:hidden absolute top-18 left-0 w-full bg-white/60 backdrop-blur-md z-50 p-4"
  >
    <ul class="space-y-3 text-white text-center">
      <li>
        <NuxtLink to="/" class="block">Favorilerim</NuxtLink>
      </li>
      <li>
        <NuxtLink to="/" class="block">Türkçe</NuxtLink>
      </li>
      <li>
        <button class="block">acililahmacun</button>
      </li>
    </ul>
  </div>
 
  <div
    v-if="searchOpen"
    class="md:hidden absolute top-18 left-0 w-full bg-[#070B14] z-50 p-4"
    ref="elSearchbar"
  >
    <HeaderSearchbar />
  </div>
</template>

<script setup>
import { onClickOutside } from "@vueuse/core";

const target = ref(null);
const searchButton = ref(null);
const elSearchbar = ref(null);
const show = ref(false);
const menuOpen = ref(false);
const searchOpen = ref(false);
onClickOutside(target, (event) => (show.value = false));
onClickOutside(searchButton, (event) => (searchOpen.value = false));
const toggleSearch = () => {
  searchOpen.value = !searchOpen.value;
  // Arama açıldığında menüyü kapat
  if (searchOpen.value) {
    menuOpen.value = false;
  }
};
const AccountMenu=[{id:1, name:"Favorilerim", url:"",icon:"mdi:heart-outline"},
{id:2, name:"Türkçe", url:"",icon:"openmoji:flag-turkey",icon2:"mingcute:down-line"},
{id:3, name:"acililahmacun", url:""},
]
const menu = [
  {
    id: 1,
    name: "acililahmacun",
    AccountId: "2020469136",
    url: "",
    img: "accountOpenMenu/premium.png",
  },
  {
    id: 2,
    name: "EPINPAY STORE CREDIT",
    url: "",
    point: 100,
    img: "accountOpenMenu/star.png",
  },
  {
    id: 3,
    name: "EPINPAY POINT",
    url: "",
    point: 100,
    img: "accountOpenMenu/smile.png",
  },
  {
    id: 4,
    name: "INVITE FRIENDS & START EARING!",
    url: "",
    img: "accountOpenMenu/accountImg.png",
  },
  { id: 5, name: "OVERVIEW", url: "", icon: "mingcute:down-fill" },
  { id: 6, name: "PURCHASE ORDERS", url: "" },
  { id: 7, name: "SELLING", url: "" },
  { id: 8, name: "EPINPAY AFFILIATE PROGRAM", url: "" },
  {
    id: 9,
    name: "SETTINGS",
    url: "",
    img: "accountOpenMenu/settings.png",
  },
  { id: 10, name: "LOG OUT", url: "", img: "accountOpenMenu/logout.png" },
];
</script>
