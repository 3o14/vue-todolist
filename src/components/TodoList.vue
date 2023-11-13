<script setup>
import { useCounterStore } from "@/stores/counter";
import TodoListItem from "./TodoListItem.vue";

const store = useCounterStore();
</script>

<template>
  <div>
    <TodoListItem v-for="todo in store.todos" :key="todo.id" :todo="todo" />
  </div>
</template>

<style scoped></style>
