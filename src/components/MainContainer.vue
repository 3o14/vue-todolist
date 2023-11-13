<script setup>
import TodoForm from "./TodoForm.vue";
import TodoList from "./TodoList.vue";
import HeadInfoDiv from "./HeadInfoDiv.vue";
</script>

<template>
  <div class="main">
    <div>
      <HeadInfoDiv />
      <TodoList />
    </div>
    <TodoForm />
  </div>
</template>

<style scoped>
.main {
  background-color: white;
  min-height: 70vh;
  overflow-y: visible;
  flex-wrap: nowrap;
  padding: 2rem;

  display: flex;
  flex-direction: column;
  justify-content: space-between;
}
</style>
