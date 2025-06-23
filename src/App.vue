<script setup>
import Calendar from "./components/Calendar.vue";
let date = new Date();

let month = date.getMonth();
let months = [
  "Январь",
  "Февраль",
  "Март",
  "Апрель",
  "Май",
  "Июнь",
  "Июль",
  "Август",
  "Сентябрь",
  "Октябрь",
  "Ноябрь",
  "Декабрь",
];
</script>
<template>
  <div class="wrapper">
    <div class="calendar">
      <h1 class="calendar__header">{{ months[month] }}</h1>
      <!-- Отображение нынешнего месяца в заголовке -->
      <div class="calendar-content">
        <Calendar></Calendar>
      </div>
    </div>
  </div>
</template>
<style scoped>
.wrapper {
  height: 80vh;
  display: flex;
  align-items: center;
  justify-content: center;
}

.calendar-content {
  border: 1px solid black;
}

.calendar__header {
  margin: 0 0 20px 0;
}
</style>
