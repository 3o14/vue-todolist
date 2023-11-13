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
    <div class="left-side">
      <div class="today-div">
        <div id="day">
          {{ dateInfo.day }}
        </div>
        <div class="month-year-div">
          <p id="month">{{ dateInfo.month }}</p>
          <p id="year">{{ dateInfo.year }}</p>
        </div>
      </div>
    </div>
    <div class="right-side">
      <div class="done-area">
        {{ store.doneTodosCount }} <span id="done">done</span>
      </div>
      <div id="weekday-div">
        {{ dateInfo.weekday }}
      </div>
    </div>
  </div>
</template>

<style scoped>
#month {
  color: #6f707e;
}

#year {
  color: #b4b5bc;
}

#day {
  color: #606271;
  font-size: 2.3rem;
  padding-right: 0.4rem;
}

#weekday-div {
  font-size: 0.8rem;
  color: #6f707e;
}
.today-div {
  display: flex;
}

.month-year-div {
  display: flex;
  flex-direction: column;
  align-items: flex-start;
}

.done-area {
  font-size: 1.5rem;
  color: #4edda1;
}

.right-side {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}

.head {
  display: flex;
  justify-content: space-between;
  height: 1.7rem;
  margin-bottom: 4rem;
}

#done {
  font-size: 0.9rem;
}
</style>
