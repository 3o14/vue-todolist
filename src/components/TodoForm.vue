<script setup>
import { ref } from "vue";
import { useCounterStore } from "@/stores/counter";

const store = useCounterStore();
const todoText = ref("");
const formElem = ref(null);

const createTodo = (todoText) => {
  store.addTodo(todoText);
  formElem.value.reset();
};
</script>

<template>
  <div>
    <form @submit.prevent="createTodo(todoText)" ref="formElem">
      <input type="text" v-model="todoText" />
      <input type="submit" />
    </form>
  </div>
</template>

<style scoped></style>
