<script setup>
import TodoForm from "./TodoForm.vue";
import TodoList from "./TodoList.vue";
import HeadInfoDiv from "./HeadInfoDiv.vue";
import { ref } from "vue";
import { useCounterStore } from "@/stores/counter";

const store = useCounterStore();
const todo = ref("");
const clickPlus = () => {
  store.addTodo(todo.value);
};

const handleInput = (value) => {
  console.log(value._value);
  todo.value = value._value;
  return value._value;
};
</script>

<template>
  <div class="layout">
    <div class="main">
      <div class="content">
        <HeadInfoDiv />
        <TodoList />
      </div>
      <TodoForm @input="handleInput" />
    </div>
    <button @click="clickPlus" id="btn">+</button>
  </div>
</template>

<style scoped>
.layout {
  display: flex;
  flex-direction: column;
  align-items: center;
}
.main {
  background-color: white;
  height: 70vh;
  overflow-y: visible;
  flex-wrap: nowrap;
  padding: 3rem;

  display: flex;
  flex-direction: column;
  justify-content: space-between;
}

.content {
  height: 85%;
}

#btn {
  width: 4rem;
  height: 4rem;
  font-size: 3rem;
  color: white;
  background-color: #4edda1;
  border: none;
  border-radius: 40rem;
  line-height: 4.5rem;
  position: relative;
  bottom: 2rem;
}
</style>
