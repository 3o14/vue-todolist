<script setup>
import { useCounterStore } from "@/stores/counter";
import TodoListItem from "./TodoListItem.vue";

const store = useCounterStore();
</script>

<template>
  <div class="list">
    <TodoListItem v-for="todo in store.todos" :key="todo.id" :todo="todo" />
  </div>
</template>

<style scoped>
.list {
  max-height: 77%;
  overflow: auto;
}
</style>
