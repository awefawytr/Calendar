<script setup>
import Calendar from "./components/Calendar.vue";

let monthsOrder = 0;
</script>
<template>
  <div class="wrapper">
    <Calendar v-for="month in 12" :monthsOrder="monthsOrder++">
      {{ month }}
    </Calendar>
  </div>
</template>
<style scoped>
.wrapper {
  gap: 15px;
  flex-wrap: wrap;
  display: flex;
  align-items: center;
  justify-content: center;
  padding: 0 0 20px 0;
}
</style>
