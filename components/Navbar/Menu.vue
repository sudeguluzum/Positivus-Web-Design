<template>
  <div
    class="bg-white rounded-2xl p-6 mx-4 mt-4 flex items-center justify-between gap-6"
  >
    <div class="flex">
      <div class="flex-center">
        <h1 class="font-semibold text-xl">PIXLS</h1>
      </div>
      <div class="flex mx-8">
        <div
          v-for="(i, j) in NavbarMenu"
          :class="[
            'flex-center mx-3 ',
            i.icon ? 'text-black gap-1 text-nowrap font-medium' : 'text-gray-500',
          ]"
        >
          {{ i.name }}
          <Icon v-if="i.icon" :name="i.icon" />
        </div>
      </div>

      <div class="flex items-center">

        <div class="absolute z-10 p-2 flex  border-gray-300 rounded-full bg-[#e7e7e7]">
          <Icon name="lets-icons:search-duotone" class="text-2xl" />
        </div>

        <div class="relative hidden sm:block">
          <input
            type="search"
            placeholder="Search.."
            class="rounded-full py-2 pl-12 pr-3 bg-[#e7e7e7] w-100 border-gray-700 outline-none"
          />
        </div>

      </div>
    </div>

    <div>
      <button class="bg-[#D1FF97] py-2 px-8 rounded-full font-medium">Login</button>
    </div>
  </div>
</template>

<script setup>
const NavbarMenu = [
  { name: "Home", url: "/" },
  {
    name: "Get started",
    url: "/",
    icon: "icon-park-outline:down",
    subMenu: [
      { name: "Installion", url: "/" },
      { name: "Documantion", url: "/" },
    ],
  },
  { name: "About", url: "/" },
  { name: "Forum", url: "/" },
];
</script>
