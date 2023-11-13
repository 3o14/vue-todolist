<script setup>
import { useCounterStore } from "@/stores/counter";
const store = useCounterStore();

var currentDate = new Date();

var dateInfo = {
  weekday: currentDate.toLocaleDateString("en-US", { weekday: "long" }),
  year: currentDate.toLocaleDateString("en-US", { year: "numeric" }),
  month: currentDate.toLocaleDateString("en-US", { month: "short" }),
  day: currentDate.toLocaleDateString("en-US", { day: "numeric" }),
};
</script>

<template>
  <div class="head">
    <div class="date-area">
      <div class="today-div">
        <div>
          {{ dateInfo.day }}
        </div>
        <div class="month-year-div">
          <p>{{ dateInfo.month }}</p>
          <p>{{ dateInfo.year }}</p>
        </div>
      </div>
      <div class="weekday-div">
        {{ dateInfo.weekday }}
      </div>
    </div>
    <div class="done-area">{{ store.doneTodosCount }}</div>
  </div>
</template>

<style scoped>
.month-year-div {
  
}
</style>
