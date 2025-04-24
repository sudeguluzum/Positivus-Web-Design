<template>
  <div class="flex flex-col md:flex-row items-center gap-3">
    <div>
      <NuxtLink to="/" class="text-white flex items-center">
        <Icon name="mdi:heart-outline" class="w-5 h-5 text-green-700 mr-1" />
        Favorilerim
      </NuxtLink>
    </div>
    <div>
      <NuxtLink to="/" class="text-white flex items-center">
        <Icon name="openmoji:flag-turkey" class="text-2xl mr-1" /> Türkçe
        <Icon name="mingcute:down-line" class="w-5 h-5 text-white ml-1" />
      </NuxtLink>
    </div>
    <div
      ref="target"
      class="max-md:hidden relative h-7 px-3 flex items-center text-white rounded-full bg-gradient-to-r from-[#1b9a88] to-[#1C3E7E]"
    >
      <NuxtLink to="/" class="flex-center relative" @click="toggleDropdown">
        acililahmacun
      </NuxtLink>
      <div
        class="absolute top-full right-0 md:right-0 md:left-auto left-1/2 transform md:translate-x-0 -translate-x-1/2 w-80 z-60 bg-white/60 backdrop-blur-md text-black text-sm rounded-b-3xl mt-2"
      >
        <HeaderDropDownMenuComp
          v-if="showDropdown"
          class="border-t border-gray-300 py-4"
          v-for="(i, index) in DropDownMenu"
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
    </div>
  </div>
</template>
<script setup>
import { onClickOutside } from "@vueuse/core";

const showDropdown = ref(false);
const target = ref(null);
const toggleDropdown = () => {
  showDropdown.value = !showDropdown.value;
};

onClickOutside(target, () => {
  showDropdown.value = false;
});

const DropDownMenu = [
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
