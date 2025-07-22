<template>
  <div class="grid grid-cols-2">
    <form action="">
      <div class="flex flex-col gap-6">
        <div class="flex gap-6">
          <label class="flex items-center gap-2">
            <input
              type="radio"
              name="contactOption"
              value="sayHi"
              class="w-5 h-5"
            />
            <span>Say Hi</span>
          </label>

          <label class="flex items-center gap-2">
            <input
              type="radio"
              name="contactOption"
              value="getQuote"
              class="w-5 h-5"
            />
            <span>Get a Quote</span>
          </label>
        </div>
        <label class="flex flex-col gap-2">
          <span class="text-sm">Name</span>
          <input
            type="text"
            placeholder="Name"
            class="border border-gray-500 outline-none rounded-xl px-3 py-2"
        /></label>
        <label class="flex flex-col gap-2">
          <span class="text-sm">Email*</span>
          <input
            type="text"
            placeholder="Email"
            class="border border-gray-500 outline-none rounded-xl px-3 py-2"
        /></label>
        <label class="flex flex-col gap-2">
          <span class="text-sm">Message*</span>
          <textarea
            type="text-area"
            rows="4"
            placeholder="Message..."
            class="border border-gray-500 outline-none rounded-xl px-3 py-2"
          />
        </label>
        <button
          class="px-15 py-3 c-black rounded-xl text-white hover:scale-102 text-center"
        >
          Send Message
        </button>
      </div>
    </form>
    <div class="h-110 hidden md:block">
      <NuxtImg src="anasayfa/contact.png" class="h-full rotate-180" />
    </div>
  </div>
</template>

<script setup></script>
