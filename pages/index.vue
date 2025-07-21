<template>
  <div class="min-h-screen px-4">
    <div class="my-10 w-full max-w-screen-xl mx-auto">
      <div class="grid grid-cols-1 md:grid-cols-2 my-10 max-h-120">
        <div class="flex flex-col justify-between">
          <h1 class="text-3xl md:text-6xl font-semibold leading-[1.5]">
            Navigating the <br />
            digital landscape <br />
            for success
          </h1>
          <!-- <div class="w-1/2 md:hidden">
            <NuxtImg src="anasayfa/right1.png" />
          </div> -->
          <p class="text-sm md:text-lg py-5">
            Our digital marketing agency helps businesses <br />
            grow and succeed online through a range of <br />
            services including SEO, PPC, social media marketing, <br />
            and content creation.
          </p>
          <div>
            <button
              class="w-full md:w-auto px-6 py-3 c-black rounded-xl text-white hover:scale-102"
            >
              Book a consultation
            </button>
          </div>
        </div>
        <div class="hidden md:block">
          <NuxtImg src="anasayfa/right1.png" />
        </div>
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
      <Line v-for="(i, j) in line1" :key="j" :title="i.title" :text="i.text" />
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
          <NuxtImg src="anasayfa/right2.png" class="object-contain w-80" />
        </div>
      </div>
      <Line v-for="(i, j) in line2" :key="j" :title="i.title" :text="i.text" />

      <IndexGreyCard :cases="caseList" />
      <Line v-for="(i, j) in line3" :key="j" :title="i.title" :text="i.text" />
      <Steps
        v-for="(i, j) in steps"
        :key="j"
        :no="i.no"
        :title="i.title"
        :text="i.text"
        class="my-5"
      />
      <Line v-for="(i, j) in line4" :key="j" :title="i.title" :text="i.text" />
      <div class="grid grid-cols-1 md:grid-cols-3 gap-8">
        <TeamCard
          v-for="(i, j) in team"
          :key="j"
          :img="i.img"
          :name="i.name"
          :departman="i.departman"
          :info="i.info"
        />
      </div>

      <div class="flex justify-end mt-6">
        <NuxtLink
          class="px-15 py-3 c-black rounded-xl text-white hover:scale-102 text-center"
        >
          <button>See all team</button>
        </NuxtLink>
      </div>
      <Line v-for="(i, j) in line5" :key="j" :title="i.title" :text="i.text" />
      <Line v-for="(i, j) in line6" :key="j" :title="i.title" :text="i.text" />
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

const line1 = [
  {
    title: "Services",
    text: "At our digital marketing agency, we offer a range of services to <br /> help businesses grow and succeed online. These services include:",
  },
];
const line2 = [
  {
    title: "Case Studies",
    text: "Explore Real-Life Examples of Our Proven Digital Marketing <br /> Success through Our Case Studies",
  },
];
const line3 = [
  {
    title: "Our Working Process ",
    text: "Step-by-Step Guide to Achieving <br /> Your Business Goals",
  },
];
const line4 = [
  {
    title: "Team",
    text: "Meet the skilled and experienced team behind our <br /> successful digital marketing strategies",
  },
];
const line5 = [
  {
    title: "Testimonials",
    text: "Hear from Our Satisfied Clients: Read Our Testimonials <br /> to Learn More about Our Digital Marketing Services",
  },
];
const line6 = [
  {
    title: "Contact Us",
    text: "Connect with Us: Let's Discuss Your <br /> Digital Marketing Needs",
  },
];
const cards = [
  {
    title: "Search engine <br> optimization",
    img: "anasayfa/index-card/p1.png",
    okImg: "anasayfa/index-card/green-ok.png",
    bgClass: "c-white",
    highlightClass: "c-green text-black",
  },
  {
    title: "Pay-per-click <br> advertising",
    img: "anasayfa/index-card/p2.png",
    okImg: "anasayfa/index-card/green-ok.png",
    bgClass: "c-green",
    highlightClass: "bg-white text-black",
    moreClass: "group-hover:bg-white",
  },
  {
    title: "Social Media <br> Marketing",
    img: "anasayfa/index-card/p3.png",
    okImg: "anasayfa/index-card/white-ok.png",
    bgClass: "c-black",
    highlightClass: "bg-white text-black",
    moreClass: "text-white group-hover:text-black",
  },
  {
    title: "Email <br> Marketing",
    img: "anasayfa/index-card/p4.png",
    okImg: "anasayfa/index-card/green-ok.png",
    bgClass: "c-white",
    highlightClass: "c-green text-black",
  },
  {
    title: "Content <br> Creation",
    img: "anasayfa/index-card/p5.png",
    okImg: "anasayfa/index-card/green-ok.png",
    bgClass: "c-green",
    highlightClass: "bg-white text-black",
    moreClass: "group-hover:bg-white",
  },
  {
    title: "Analytics and <br> Tracking",
    img: "anasayfa/index-card/p6.png",
    okImg: "anasayfa/index-card/white-ok.png",
    bgClass: "c-black",
    highlightClass: "c-green text-black",
    moreClass: "text-white group-hover:text-black",
  },
];

const caseList = [
  {
    text: "For a local restaurant, we implemented a targeted PPC campaign that resulted in a 50% increase in website traffic and a 25% increase in sales.",
    url: "#",
  },
  {
    text: "For a B2B software company, we developed an SEO strategy that resulted in a first page ranking for key keywords and a 200% increase in organic traffic.",
    url: "#",
  },
  {
    text: "For a national retail chain, we created a social media marketing campaign that increased followers by 25% and generated a 20% increase in online sales.",
    url: "#",
  },
];
const steps = [
  {
    no: "01",
    title: "Consultation",
    text: "During the initial consultation, we will discuss your business goals and objectives, target audience, and current marketing efforts. This will allow us to understand your needs and tailor our services to best fit your requirements.",
  },
  {
    no: "02",
    title: "Research and Strategy Development",
    text: "During the initial consultation, we will discuss your business goals and objectives, target audience, and current marketing efforts. This will allow us to understand your needs and tailor our services to best fit your requirements.",
  },
  {
    no: "03",
    title: "Implementation",
    text: "During the initial consultation, we will discuss your business goals and objectives, target audience, and current marketing efforts. This will allow us to understand your needs and tailor our services to best fit your requirements.",
  },
  {
    no: "04",
    title: "Monitoring and Optimization",
    text: "During the initial consultation, we will discuss your business goals and objectives, target audience, and current marketing efforts. This will allow us to understand your needs and tailor our services to best fit your requirements.",
  },
  {
    no: "05",
    title: "Reporting and Communication",
    text: "During the initial consultation, we will discuss your business goals and objectives, target audience, and current marketing efforts. This will allow us to understand your needs and tailor our services to best fit your requirements.",
  },
  {
    no: "06",
    title: "Continual Improvement",
    text: "During the initial consultation, we will discuss your business goals and objectives, target audience, and current marketing efforts. This will allow us to understand your needs and tailor our services to best fit your requirements.",
  },
];

const team = [
  {
    name: "Sude Gül ÜZÜM",
    img: "anasayfa/teams/t1.png",
    departman: "CEO and Founder",
    info: "10+ years of experience in digital marketing. Expertise in SEO, PPC, and content strategy",
  },
  {
    name: "Sude Gül ÜZÜM",
    img: "anasayfa/teams/t1.png",
    departman: "CEO and Founder",
    info: "10+ years of experience in digital marketing. Expertise in SEO, PPC, and content strategy",
  },
  {
    name: "Sude Gül ÜZÜM",
    img: "anasayfa/teams/t1.png",
    departman: "CEO and Founder",
    info: "10+ years of experience in digital marketing. Expertise in SEO, PPC, and content strategy",
  },
  {
    name: "Sude Gül ÜZÜM",
    img: "anasayfa/teams/t1.png",
    departman: "CEO and Founder",
    info: "10+ years of experience in digital marketing. Expertise in SEO, PPC, and content strategy",
  },
  {
    name: "Sude Gül ÜZÜM",
    img: "anasayfa/teams/t1.png",
    departman: "CEO and Founder",
    info: "10+ years of experience in digital marketing. Expertise in SEO, PPC, and content strategy",
  },
  {
    name: "Sude Gül ÜZÜM",
    img: "anasayfa/teams/t1.png",
    departman: "CEO and Founder",
    info: "10+ years of experience in digital marketing. Expertise in SEO, PPC, and content strategy",
  },
];
</script>
