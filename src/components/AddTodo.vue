<template>
  <div>
    <input class="input" type="text" placeholder="add todo" v-model="newTodo" />
    <button class="btn-add" @click="addTodo">Add</button>
  </div>
</template>

<script setup>
import { ref, defineEmits } from "vue";

const emits = defineEmits(["add-todo"]);

const newTodo = ref("");

const addTodo = () => {
  if (newTodo.value.trim() !== "") {
    emits("add-todo", newTodo.value);
    newTodo.value = "";
  }
};
</script>

<style scoped>
.input {
  margin-right: 10px;
  width: 160px;
  height: 20px;
}
.btn-add {
  width: 60px;
  height: 26px;
}
</style>
