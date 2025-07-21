<template>
  <div
    :class="[
      'flex flex-col gap-5 border p-5 md:p-8 rounded-4xl border-b-6 transition-all duration-500 hover:scale-101',
      isOpen ? 'c-green' : 'c-white',
    ]"
  >
    <div class="flex justify-between cursor-pointer" @click="toggle">
      <span class="flex-center font-semibold gap-3">
        <h1 class="text-3xl md:text-5xl">{{ no }}</h1>
        <h2 class="text-lg md:text-2xl">{{ title }}</h2>
      </span>

      <Icon v-if="isOpen" name="lsicon:minus-outline" class="text-5xl" />
      <Icon v-else name="icons8:plus" class="text-5xl" />
    </div>

    <div v-show="isOpen" class="pt-5 border-t">
      <p>{{ text }}</p>
    </div>
  </div>
</template>

<script setup>
const props = defineProps({
  no: String,
  title: String,
  text: String,
});

const isOpen = ref(false);
const toggle = () => {
  isOpen.value = !isOpen.value;
};
</script>
