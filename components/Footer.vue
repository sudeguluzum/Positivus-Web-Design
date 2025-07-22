<template>
  <div
    class="w-full max-w-screen-xl md:mx-auto c-black p-10 mx-4 rounded-t-4xl text-white"
  >
    <div class="flex flex-col items-center justify-between lg:flex-row gap-10">
      <NuxtImg src="whiteLogo.png" class="h-5 md:h-6" />
      <div
        class="flex flex-col md:flex-row gap-6 md:underline underline-offset-2 text-nowrap"
      >
        <button
          v-for="(i, j) in footerMenu"
          class="hover:scale-102 hover:text-lime-300"
        >
          {{ i.name }}
        </button>
      </div>

      <div class="text-2xl flex gap-3">
        <Icon name="entypo-social:linkedin-with-circle" />
        <Icon name="ic:baseline-facebook" />
        <Icon name="prime:twitter" />
      </div>
    </div>
    <div class="flex flex-col md:flex-row justify-between border-b py-10 gap-6">
      <div class="flex flex-col gap-2 items-center md:items-start">
        <button class="c-green px-1 rounded-lg text-black w-fit">
          Contact us:
        </button>
        <p>Email: info@positivus.com</p>
        <p>Phone: 555-567-8901</p>
        <p>Address: 1234 Main St Moonstone City</p>
      </div>
      <div
        class="bg-[#292a32] flex flex-col md:flex-row gap-3 rounded-2xl px-7 py-10"
      >
        <input
          type="text"
          placeholder="Email"
          class="border border-gray-500 outline-none rounded-xl px-3 py-3"
        />
        <button
          class="text-nowrap px-10 py-3 c-green rounded-xl text-black hover:scale-102 text-center"
        >
          Subscribe to news
        </button>
      </div>
    </div>
  </div>
</template>

<script setup>
const footerMenu = [
  { name: "About us" },
  { name: "Services" },
  { name: "Use Cases" },
  { name: "Pricing" },
  { name: "Blog" },
];
</script>
