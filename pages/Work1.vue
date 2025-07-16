<template>
  <h3>{{ title }}</h3>
  <input type="text" v-model="title" class="border rounded-md p-1" />
  <button @click="inc" class="border rounded bg-pink-400 p-1">
    {{ counter }}
  </button>
  <hr />
  <Work1OddOrEvent :counter="counter" @odd-event="alertMe" />
</template>

<script setup>
import { onMounted } from 'vue';
const title = ref("Başlık");
const counter = ref(0);
const inc = () => {
  counter.value++;
};

const alertMe = (info) => {
  console.log(info);
};

onMounted(()=>{
    console.log("Mounted esnasında yapılabilecek.")
})
</script>
