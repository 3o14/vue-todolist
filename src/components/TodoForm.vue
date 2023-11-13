<script setup>
import { ref, onUpdated } from "vue";
import { useCounterStore } from "@/stores/counter";

const store = useCounterStore();
const todoText = ref("");
const formElem = ref(null);

const createTodo = (todoText) => {
  store.addTodo(todoText);
  formElem.value.reset();
  todoText.value = "";
};

const emit = defineEmits(["input"]);

const updateParent = () => {
  emit("input", todoText);
};

</script>

<template>
  <form class="form" @submit.prevent="createTodo(todoText)" ref="formElem">
    <div>
      <input
        placeholder="할 일을 입력하세요"
        id="input"
        type="text"
        required
        v-model="todoText"
        @input="updateParent"
      />
      <span></span>
    </div>
  </form>
</template>

<style scoped>
div {
  position: relative;
}

.form {
  display: flex;
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
