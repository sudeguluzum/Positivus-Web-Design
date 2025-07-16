<template>
<section>
    <input @keydown.enter="AddTodo($event.target.value)" type="text" placeholder="Nedir?" class="w-full border rounded border-[#7CB930] px-1 my-2 focus:outline-none">
</section>
</template>

<script setup>

const props =defineProps({AddTodo: {type: Function}})
</script>