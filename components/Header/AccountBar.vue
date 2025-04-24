<template>
  <div class="flex items-center gap-3">
    <!-- Mobil search ve hamburger menü -->
    <div class="md:hidden flex flex-wrap gap-2">
      <button
        ref="searchButton"
        @click="toggleSearch"
        class="w-9 h-9 mb-1.5 flex-center text-white"
      >
        <Icon name="material-symbols:search" class="text-xl" />
      </button>

      <button ref="menuButton" @click="toggleMenu">
        <Icon name="mdi:menu" class="text-white text-2xl" />
      </button>
    </div>

    <!-- Masaüstü menü -->
    <div class="hidden md:flex relative">
      <HeaderAccountBarMenu />
    </div>
  </div>

  <!-- Mobil Menü Açılır -->
  <!-- <div
    v-if="showMenu"
    class="md:hidden absolute top-18 left-0 w-full bg-[#070B14] backdrop-blur-md z-50 p-4"
    ref="elMenu"
  >
    <HeaderSideBar />
  </div> -->

  <div
    v-if="showMenu"
    class="md:hidden fixed inset-0  top-18 w-full h-full bg-[#070B14]/95 backdrop-blur-md z-50 overflow-y-auto"
    ref="elMenu"
  >
    <div class="container mx-auto p-4 pt-5">
      <HeaderSideBar />
    </div>
  </div>

  <div
    v-if="showSearch"
    class="md:hidden absolute top-18 left-0 w-full bg-[#070B14] z-50 p-4"
    ref="elSearchbar"
  >
    <HeaderSearchbar />
  </div>
</template>

<script setup>
import { onClickOutside } from "@vueuse/core";
const showSearch = ref(false);
const searchButton = ref(null);
const elSearchbar = ref(null);

const showMenu = ref(false);
const menuButton = ref(null);
const elMenu = ref(null);

const toggleSearch = () => {
  showSearch.value = !showSearch.value;
};

onClickOutside(elSearchbar, (event) => {
  const clickedButton = searchButton.value?.contains(event.target);
  if (!clickedButton) {
    showSearch.value = false;
  }
});

const toggleMenu = () => {
  showMenu.value = !showMenu.value;
};

onClickOutside(elMenu, (event) => {
  const clickedButton = menuButton.value?.contains(event.target);
  if (!clickedButton) {
    showMenu.value = false;
  }
});
</script>
