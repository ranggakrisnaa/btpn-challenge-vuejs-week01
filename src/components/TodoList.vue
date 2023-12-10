<template>
  <div>
    <h1>List To Do</h1>
    <ul>
      <li class="list-todo" v-for="(todo, index) in todos" :key="index">
        {{ todo }}
        <button @click="deleteTodo(index)">Delete</button>
      </li>
    </ul>
  </div>
</template>

<script setup>
import { defineProps } from "vue";

const props = defineProps({
  todos: {
    type: Array,
    required: true,
  },
});

const emits = defineEmits(["delete-todo"]);

const deleteTodo = (index) => {
  emits("delete-todo", index);
};
</script>

<style>
.list-todo {
  margin-top: 10px;
}
</style>
