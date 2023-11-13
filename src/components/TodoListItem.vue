<script setup>
import { useCounterStore } from "@/stores/counter";

defineProps({
  todo: Object,
});

const store = useCounterStore();
</script>

<template>
  <div class="todoItem">
    <span :class="{ 'is-done': todo.isDone }">{{ todo.text }}</span>
    <div
      id="btn"
      :class="{ 'is-done-check': todo.isDone }"
      @click="store.updateTodo(todo.id)"
    ></div>
  </div>
</template>

<style scoped>
.is-done {
  color: #dcdde3;
}

.is-done-check {
  border: 0.2rem solid #4edda1;
}

.todoItem {
  margin-bottom: 1.5rem;
  display: flex;
  justify-content: space-between;
}

#btn {
  width: 0.7rem;
  height: 0.7rem;
  background-color: none;
  border: 0.2rem solid #dcdde3;
  border-radius: 40rem;
}
</style>
