<template>
  <div>
    <AddTodo @add-todo="handleAddTodo" />
    <TodoList :todos="todos" @delete-todo="handleDeleteTodo" />
  </div>
</template>

<script setup>
import AddTodo from "./components/AddTodo.vue";
import TodoList from "./components/TodoList.vue";
import { ref } from "vue";

const todos = ref([]);

const handleAddTodo = (newTodo) => {
  todos.value = [...todos.value, newTodo];
};

const handleDeleteTodo = (index) => {
  todos.value.splice(index, 1);
};
</script>
