<template>
  <div
  >
    <div class="relative" ref="target">
      <button class="px-2 py-1 rounded-lg border" @click="show = !show">
        Acılı Lahmacun
      </button>
      <div v-if="show" class="p-2 w-64 absolute z-5 bg-red-500">
        <div>Acılı Lahmacun</div>
        <div>Parchuse Orders</div>
        <div>Orderview</div>
      </div>
    </div>
  </div>
</template>

<script setup>
import { onClickOutside } from "@vueuse/core";

const target = ref(null);
const show = ref(false);

onClickOutside(target, (event) => (show.value = false));
</script>
