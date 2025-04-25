<template>
  <div>
    <DD :items="items">
      <template #btn>
        <button>Seçilen Sude</button>
      </template>
      <template #itemSlot="{ item, index }">
        <p>#{{ index }} - {{ item }}</p>
      </template>
    </DD>
  </div>
</template>

<script setup>
const items = ["Sude", "Gül", "Üzüm"];

</script>
