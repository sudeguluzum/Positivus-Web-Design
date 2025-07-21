<template>
  <div
    :class="[
      'border border-b-6 rounded-4xl p-12 flex hover:shadow-xl hover:shadow-gray-800 hover:scale-101',
      bgClass,
    ]"
  >
    <div class="flex flex-col justify-between">
      <p
        :class="[
          'rounded-lg font-semibold text-2xl md:text-4xl p-1 w-fit',
          highlightClass,
        ]"
      >
        {{ title }}
      </p>
      <span class="flex items-center gap-2 font-semibold group">
        <NuxtImg
          :src="okImg"
          class="w-10 transition-transform duration-500 group-hover:rotate-[390deg]"
        />
        <p
          :class="[
            'transition-colors group-hover:bg-[#B9FF66] p-1 rounded-r-2xl rounded',
            moreClass,
          ]"
        >
          Learn More
        </p>
      </span>
    </div>
    <div class="w-58 h-58 flex-center">
      <NuxtImg :src="img" />
    </div>
  </div>
</template>

<script setup>
const props = defineProps({
  title: String,
  img: String,
  okImg: String,
  bgClass: {
    type: String,
    default: "c-white",
  },
  highlightClass: {
    type: String,
    default: "c-green",
  },
  moreClass: {
    type: String,
    default: "text-black",
  },
});

// const bgClass = computed(() => {
//   switch (props.bgClass) {
//     case "green":
//       return "c-green";
//     case "white":
//       return "c-white";
//     case "black":
//       return "c-black";
//     default:
//       return "c-white";
//   }
// });

// const highlightClass = computed(() => {
//   switch (props.highlightClass) {
//     case "green":
//       return "c-green";
//     case "white":
//       return "c-white";
//     case "black":
//       return "c-black";
//     default:
//       return "c-white";
//   }
// });
</script>
