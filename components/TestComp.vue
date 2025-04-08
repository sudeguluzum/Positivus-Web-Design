<template>
  <p>Selam</p>
  <p>{{ name }}</p>
</template>

<script setup>
const props = defineProps(["name"]);
console.log(props.name);
</script>
