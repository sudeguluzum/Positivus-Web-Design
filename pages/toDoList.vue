<template>
  <div class="w-screen min-h-screen bg-[#e9e9e9] pt-10">
    <div class="bg-[#D1FF97] rounded-lg shadow-2xl w-1/3 mx-auto p-3">
      <h3 class="text-2xl text-center font-semibold">To Do List</h3>
      <ListeAddSection :AddTodo="AddTodo" />
      <ListeTodoList :todoList="todoList" />
    </div>
  </div>
</template>

<script setup>
const todoList = ref([]);
const AddTodo = (todoText) => {
  console.log(todoText);
  todoList.value.push({
    id: new Date().getTime(),
    title: todoText,
  });
};
</script>
