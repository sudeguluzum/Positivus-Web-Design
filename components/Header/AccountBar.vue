<template>
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
            class="absolute top-full right-0 w-80 z-30 bg-white text-black text-sm rounded-b-3xl mt-2"
          >
            <div
              v-for="(i, index) in menu"
              :key="index"
              class="border-t border-gray-300 py-4"
            >
              <NuxtLink :to="i.url">
                <div class="flex items-center justify-between px-4">
                  <div class="flex flex-col">
                    <span
                      class="text-sm"
                      :class="{ 'font-bold': i.id === 1 }"
                      >{{ i.name }}</span
                    >

                    <span
                      v-if="i.id === 1"
                      class="text-sm text-center text-gray-500"
                    >
                      Account ID: {{ i.AccountId }}</span
                    >
                  </div>
                  <div class="flex-center">
                    <span class="text-sm font-bold px-2">{{ i.point }}</span>
                    <Icon
                      v-if="i.icon"
                      :name="i.icon"
                      class="text-2xl text-black"
                    />
                    <NuxtImg :src="i.img" class="h-5" />
                  </div>
                </div>
              </NuxtLink>
            </div>
          </div>
        </li>
      </ul>
    </div>
  </div>
  <!-- Mobil Menü Açılır -->
  <div
    v-if="menuOpen"
    class="md:hidden absolute top-18 left-0 w-full bg-[#070B14] z-50 p-4"
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
</template>

<script setup>
const menuOpen = ref(false);
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
import { onClickOutside } from "@vueuse/core";

const target = ref(null);
const show = ref(false);

onClickOutside(target, (event) => (show.value = false));
</script>
