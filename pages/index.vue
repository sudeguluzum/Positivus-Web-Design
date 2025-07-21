<template>
  <div class="min-h-screen">
    <div class="my-10 w-full max-w-screen-xl mx-auto md:px-4">
      <Header />
      <div class="flex my-10 max-h-120">
        <div class="w-1/2 flex flex-col justify-between">
          <h1 class="text-5xl font-semibold leading-[1.5]">
            Navigating the <br />
            digital landscape <br />
            for success
          </h1>
          <p>
            Our digital marketing agency helps businesses <br />
            grow and succeed online through a range of <br />
            services including SEO, PPC, social media marketing, <br />
            and content creation.
          </p>
          <div>
            <button
              class="px-6 py-3 c-black rounded-xl text-white hover:scale-102"
            >
              Book a consultation
            </button>
          </div>
        </div>
        <div class="w-1/2"><NuxtImg src="anasayfa/right1.png" /></div>
      </div>
      <div class="my-25">
        <Swiper
          :slides-per-view="6"
          space-between="20"
          :loop="true"
          :modules="modules"
          :autoplay="{ delay: 5000 }"
          :breakpoints="{
            '1': {
              slidesPerView: 1,
            },
            '400': {
              slidesPerView: 2,
            },
            '640': {
              slidesPerView: 3,
            },
            '800': {
              slidesPerView: 4,
            },
            '1200': {
              slidesPerView: 5,
            },
          }"
        >
          <swiper-slide v-for="(i, j) in logo" :key="j">
            <NuxtImg :src="i.img" class="object-contain grayscale h-12"
          /></swiper-slide>
        </Swiper>
      </div>
      <div class="flex gap-10">
        <h1 class="c-green p-1 font-semibold text-3xl">Services</h1>
        <p class="text-black">
          At our digital marketing agency, we offer a range of services to
          <br />
          help businesses grow and succeed online. These services include:
        </p>
      </div>
      <div class="grid grid-cols-1 sm:grid-cols-2 gap-10 mt-15">
        <IndexServices-Card
          v-for="(i, j) in cards"
          :key="j"
          :title="i.title"
          :img="i.img"
          :ok-img="i.okImg"
          :bg-class="i.bgClass"
          :highlight-class="i.highlightClass"
          :more-class="i.moreClass"
        />
      </div>
      <div class="flex my-30 max-h-80">
        <div class="w-1/2 flex flex-col justify-center gap-10 mx-20">
          <h1 class="text-2xl font-semibold">Let’s make things happen</h1>
          <p>
            Contact us today to learn more about how our digital <br />
            marketing services can help your business grow and <br />
            succeed online.
          </p>
          <div>
            <button
              class="px-6 py-3 c-black rounded-xl text-white hover:scale-102"
            >
              Get your free proposal
            </button>
          </div>
        </div>
        <div class="w-1/2 hidden md:flex items-center justify-end">
          <NuxtImg src="anasayfa/right2.png" class="object-scale-down" />
        </div>
      </div>
      <div class="flex gap-10">
        <h1 class="c-green p-1 font-semibold text-3xl">Case Studies</h1>
        <p class="text-black">
          Explore Real-Life Examples of Our Proven Digital Marketing <br />
          Success through Our Case Studies
        </p>
      </div>
      <IndexGreyCard />
    </div>
  </div>
</template>
<script setup>
import { Swiper, SwiperSlide } from "swiper/vue";
import { Autoplay, Navigation } from "swiper/modules";
import "swiper/css";

const modules = [Navigation, Autoplay];
const logo = [
  { img: "anasayfa/index-slider/p1.png" },
  { img: "anasayfa/index-slider/p2.png" },
  { img: "anasayfa/index-slider/p3.png" },
  { img: "anasayfa/index-slider/p4.png" },
  { img: "anasayfa/index-slider/p5.png" },
  { img: "anasayfa/index-slider/p6.png" },
];

const cards = [
  {
    title: "Search engine optimization",
    img: "anasayfa/index-card/p1.png",
    okImg: "anasayfa/-card/green-ok.png",
    bgClass: "c-white",
    highlightClass: "c-green text-black",
  },
  {
    title: "Pay-per-click advertising",
    img: "anasayfa/index-card/p2.png",
    okImg: "anasayfa/-card/green-ok.png",
    bgClass: "c-green",
    highlightClass: "bg-white text-black",
    moreClass: "group-hover:bg-white",
  },
  {
    title: "Social Media Marketing",
    img: "anasayfa/index-card/p3.png",
    okImg: "anasayfa/index-card/white-ok.png",
    bgClass: "c-black",
    highlightClass: "bg-white text-black",
    moreClass: "text-white group-hover:text-black",
  },
  {
    title: "Email Marketing",
    img: "anasayfa/index-card/p4.png",
    okImg: "anasayfa/index-card/green-ok.png",
    bgClass: "c-white",
    highlightClass: "c-green text-black",
  },
  {
    title: "Content Creation",
    img: "anasayfa/index-card/p5.png",
    okImg: "anasayfa/index-card/green-ok.png",
    bgClass: "c-green",
    highlightClass: "bg-white text-black",
    moreClass: "group-hover:bg-white",
  },
  {
    title: "Analytics and Tracking",
    img: "anasayfa/index-card/p6.png",
    okImg: "anasayfa/index-card/white-ok.png",
    bgClass: "c-black",
    highlightClass: "c-green text-black",
    moreClass: "text-white group-hover:text-black",
  },
];
</script>
