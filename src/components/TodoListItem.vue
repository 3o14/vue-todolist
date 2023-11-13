<script setup>
import { useCounterStore } from "@/stores/counter";
import { ref } from "vue";
const props = defineProps({
  todo: Object,
});

const store = useCounterStore();

const deleteTodo = (id) => {
  const userConfirmed = window.confirm("할 일을 삭제할까요?");

  if (userConfirmed) {
    store.deleteTodo(id);
    console.log("값이 변경되었습니다.");
  } else {
    console.log("값 변경이 취소되었습니다.");
  }
};

const checked = ref(false);
const done = () => {
  alert("hel");
  checked.value = props.todo.isDone;
};
</script>

<template>
  <div class="todoItem" @contextmenu.prevent="deleteTodo(todo.id)">
    <span :class="{ 'is-done': todo.isDone }">{{ todo.text }}</span>
    <div
      id="btn"
      :class="{ 'is-done-check': checked }"
      @click="[store.updateTodo(todo.id), done()]"
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
  width: 1rem;
  height: 1rem;
  background-color: none;
  border: 0.2rem solid #dcdde3;
  border-radius: 40rem;
}
</style>
