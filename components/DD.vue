<template>
  <div @click="show = !show">
    <slot name="btn" v-bind="{}">
      <input value="sude" />
    </slot>
  </div>
  <div v-if="show">
    <template v-for="(item, index) in items">
      <div @click="selected = item">
        <slot name="itemSlot" v-bind="{ item, index }">
          <p>{{ item }}</p>
        </slot>
      </div>
    </template>
  </div>
</template>

<script setup>
const props = defineProps({ items: { type: Array, default: [] } });
const show = ref(false);
const selected = ref(null);
</script>
