<template>
  <ListeToDoListItem v-for="todoItem in todoList" :key="todoItem.id"/>
  <small> {{toDoLength}} adet Item vardır..</small>
  <ListeSummary />
</template>

<script setup>
const props = defineProps(["todoList"])


const toDoLength = computed(()=> props.todoList.length)
</script>
