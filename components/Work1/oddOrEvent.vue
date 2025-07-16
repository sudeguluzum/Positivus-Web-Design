<template>
    <div class="bg-pink-300 text-3xl">
<h1 >sude</h1>
<h3>{{ result }}</h3>
<h3>{{ props.counter }}</h3></div>
</template>

<script setup>
const props=defineProps({counter: Number})
const emit=defineEmits();

const result=computed(()=>(props.counter %2 === 0? "Çift" : "Tek"))

watch(result, (result)=>{
    if(result === "Tek") emit("odd-event", true)
})

</script>