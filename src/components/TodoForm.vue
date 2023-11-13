<script setup>
import { ref } from "vue";
import { useCounterStore } from "@/stores/counter";

const store = useCounterStore();
const todoText = ref("");
const formElem = ref(null);

const createTodo = (todoText) => {
  store.addTodo(todoText);
  formElem.value.reset();
  todoText.value = "";
};
</script>

<template>
  <div>
    <form @submit.prevent="createTodo(todoText)" ref="formElem">
      <input
        placeholder="할 일을 입력하세요"
        id="input"
        type="text"
        required
        v-model="todoText"
      />
      <span></span>
      <!-- <input type="submit" /> -->
    </form>
  </div>
</template>

<style scoped>

div {
  position: relative;
  width: 300px;
  margin-left: 50px;
  margin-top: 100px;
}

#input {
  font-size: 15px;
  color: #222222;
  width: 300px;
  border: none;
  border-bottom: solid #aaaaaa 1px;
  padding-bottom: 10px;
  padding-left: 10px;
  position: relative;
  background: none;
  z-index: 5;
}

#input::placeholder {
  color: #aaaaaa;
}
#input:focus {
  outline: none;
}

span {
  display: block;
  position: absolute;
  bottom: 0;
  left: 0%;
  background-color: #666;
  width: 0;
  height: 2px;
  border-radius: 2px;
  transition: 0.5s;
}

#input:focus ~ span,
#input:valid ~ span {
  width: 100%;
}
</style>
