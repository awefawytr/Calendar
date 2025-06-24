<script setup>
import DaysOfMonth from "./DaysOfMonth.vue";

const props = defineProps({
  monthsOrder: {
    type: Number,
    required: true
  }
})


// console.log(props.monthsOrder);

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

let date = new Date(); // Данная дата
let year = date.getFullYear();
// let month = date.getMonth();

let month = props.monthsOrder;

let countOfDay;
let firstDay;

function getDate(year, month) {
  let date = new Date(year, month + 1, 0); // Общее количество дней
  console.log(date);
  // let firstDayMonth = new Date(year, month, 1); // Первый день недели в месяце
  let firstDayMonth = new Date(year, props.monthsOrder, 1);

  firstDay = firstDayMonth.getDay();
  if (firstDay === 0) {
    // Если воскресенье
    firstDay = 7;
  }

  countOfDay = date.getDate();
  console.log(countOfDay);
}
getDate(year, month);
</script>

<template>
  <div class="calendar">
    <h1 class="calendar__header">{{ months[props.monthsOrder] }}</h1>
    <div class="calendar-content">
      <div class="calendar-title">
        <span class="calendar-title__day" id="1">Пн</span>
        <span class="calendar-title__day" id="2">Вт</span>
        <span class="calendar-title__day" id="3">Ср</span>
        <span class="calendar-title__day" id="4">Чт</span>
        <span class="calendar-title__day" id="5">Пт</span>
        <span class="calendar-title__day" id="6">Сб</span>
        <span class="calendar-title__day" id="0">Вс</span>
      </div>
      <div class="calendar-number">
        <DaysOfMonth :countOfDay="countOfDay" :firstDay="firstDay" />
      </div>
    </div>
  </div>
</template>

<style>
.calendar {
  display: flex;
  flex-direction: column;
  height: 200px;
  justify-content: space-between;
}

.calendar-number {
  display: grid;
  grid-template-columns: repeat(7, 1fr);
  text-align: center;
}

.calendar-title {
  position: relative;
  display: grid;
  grid-template-columns: repeat(7, 50px);
}

.calendar-title__day {
  border-bottom: 1px solid black;
  border-right: 1px solid black;
  text-align: center;
}

.calendar-title__day:last-child {
  border-right: none;
}

.calendar-content {
  border: 1px solid black;
}
</style>