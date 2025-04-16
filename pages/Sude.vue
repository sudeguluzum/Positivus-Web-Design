<template>
  <div>
    {{ menuList }}
  </div>
</template>

<script setup>
const { products, menuList } = mockData();
definePageMeta({ layout: "layout" });
</script>
