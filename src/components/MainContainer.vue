<script setup>
import TodoForm from "./TodoForm.vue";
import TodoList from "./TodoList.vue";
import HeadInfoDiv from "./HeadInfoDiv.vue";
</script>

<template>
  <div class="outline">
    <div class="main">
      <div>
        <HeadInfoDiv />
        <TodoList />
      </div>
      <TodoForm />
    </div>
    <button id="btn">+</button>
  </div>
</template>

<style scoped>
.outline {
  text-align: center;
}
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

#btn {
  color: white;
  background-color: #4edda1;
  width: 4rem;
  height: 4rem;
  font-size: 3rem;
  line-height: 4.5rem;
  border-radius: 40rem;
  position: relative;
  bottom: 2rem;
}
</style>
