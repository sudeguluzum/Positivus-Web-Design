<template>
  <!-- <div class="bg-[#252627] bg-[url(/bg-img/WebBG.png)]">
   <Header />
    <ImgBar />
    <Games />
    <TrendGames />
    <NewProducts /> 
    <TrendGift />
    <TrendPayment/>
    <Text />  
  </div>
  <div class="bg-[url(/bg-img/WebBG.png)]">
    <Footer />
  </div> -->

  <div class="bg-[#e9e9e9] min-h-screen flex-center">
    <div
      class="bg-[#f7f7f7] border-3 border-white rounded-3xl w-6xl overflow-hidden my-8"
    >
      <NavbarMenu />
      <div class="w-full p-8 gap-8 relative flex md:flex-row flex-col">
        <div
          class="flex-1 h-180 text-center rounded-2xl overflow-hidden justify-between bg-amber-200 hidden md:block"
        >
          <div class="py-10 font-semibold">
            <h2 class="text-lg mb-4">LARGEST IMAGE SOURCE</h2>
            <h2 class="text-5xl leading-17">
              POWERED BY
              <div class="relative flex-center">
                <h2 class="z-50 w-full">CREATORS AROUND</h2>
                <div
                  class="absolute rounded-full bottom-1 w-84 h-5 bg-[#D1FF99]"
                ></div>
              </div>
            </h2>

            <div class="flex-center gap-3 mt-3">
              <div class="text-5xl">THE WORLD.</div>
              <div class="h-10 w-10 rounded-full relative bg-[#384A20]">
                <div
                  class="h-10 w-10 rounded-full absolute left-5 bg-[#4B7416]"
                ></div>
                <div
                  class="h-10 w-10 rounded-full absolute left-10 bg-[#7CB930]"
                ></div>
                <div
                  class="h-10 w-10 rounded-full absolute left-15 bg-[#B5FF56]"
                ></div>
              </div>
            </div>

            <div class="my-13 flex flex-col items-center">
              <p class="text-gray-400 font-normal">Don't have account?</p>
              <div class="flex-center gap-2 border-b w-40 mt-4">
                <p>Create account</p>
                <Icon name="line-md:arrow-right" />
              </div>
            </div>
          </div>
          <div
            class="relative rounded-2xl overflow-hidden h-60 w-full flex-center"
          >
            <NuxtImg
              src="proje/car4.png"
              class="w-full h-full object-cover grayscale"
            />
            <div class="absolute flex justify-center gap-6 px-20">
              <p class="text-white text-nowrap">About us</p>
              <div>
                <p class="text-white text-left">
                  Over <span class="font-semibold">3 million </span> free
                  <span class="font-semibold">hight-resolution</span> images
                  brought to you by the world's most generous comminity of
                  <span class="font-semibold">photographers.</span>
                </p>
              </div>
            </div>
          </div>
        </div>
        <div
          class="flex-center flex-1 h-180 relative rounded-2xl overflow-hidden bg-amber-600"
        >
          <Swiper
            :loop="true"
            :modules="modules"
            :autoplay="{ delay: 5000 }"
            :navigation="{
              nextEl: '.custom-next',
              prevEl: '.custom-prev',
            }"
            class="relative z-0"
          >
            <swiper-slide v-for="(i, j) in cars" :key="j">
              <NuxtImg :src="i.img" class="w-full h-full object-fill grayscale"
            /></swiper-slide>
          </Swiper>

          <div class="absolute w-100 flex-center flex-col rounded-2xl z-10">
            <div class="bg-white/50 w-full rounded-t-2xl rounded-b text-center">
              <p class="font-semibold py-3">Login to your account</p>
            </div>

            <div
              class="bg-white/50 rounded-t rounded-b-2xl w-full flex flex-col gap-6 py-5 text-black"
            >
              <div class="flex flex-col px-5 rounded-t">
                <label for="username" class="text-xs">Username</label>
                <input
                  type="text"
                  class="border-b border-gray-400 outline-none text-white"
                />
              </div>

              <div class="flex flex-col mx-5">
                <label for="password" class="text-xs">Password</label>
                <input
                  type="password"
                  class="border-b border-gray-400 outline-none"
                />
              </div>

              <div class="flex justify-between px-5">
                <div class="flex items-center flex-1">
                  <input type="checkbox" class="h-4 w-4 accent-[#D1FF99]" />
                  <label for="remember" class="ml-2 text-sm">Remember me</label>
                </div>
                <div class="flex flex-1 justify-end">
                  <p class="text-xs">Forgot your password?</p>
                </div>
              </div>
              <div class="px-5">
                <button class="bg-black text-white rounded-2xl w-full p-2">
                  login
                </button>
              </div>
            </div>
          </div>

          <div class="absolute bottom-8 right-8 flex z-10 gap-4 ">
            <button class="custom-prev flex-center border rounded border-white/30 p-1"> <Icon name="mdi:chevron-left" size="24" class="text-white" /></button>
            <button class="custom-next flex-center border rounded border-white/30 p-1"><Icon name="mdi:chevron-right" size="24" class="text-white"/></button>
           
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
<script setup>
import { Swiper, SwiperSlide } from "swiper/vue";
import { Autoplay, Navigation } from "swiper/modules";
import "swiper/css";

const modules = [Navigation, Autoplay];
const cars = [
  { img: "proje/s1.png" },
  { img: "proje/s2.png" },
  { img: "proje/s3.png" },
  { img: "proje/s4.png" },
  { img: "proje/s5.png" },
];
</script>
