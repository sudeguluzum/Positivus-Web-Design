<template>
  <div
    class="bg-[#f7f7f7] flex justify-between items-center px-2 p-1 my-1 rounded even:bg-[#E7E7E7]"
  >
    <label for="completed"
      ><input
      v-model="TodoList.completed"
        type="checkbox"
        id="completed"
        class="mr-2 accent-[#7CB930]"
      /></label
    >
    <button class="text-[#7CB930] active:text-[#384A20]">
      <Icon name="line-md:trash" />
    </button>
  </div>
</template>

<script setup></script>
