<script setup>
import Calendar from "./components/Calendar.vue";
</script>
<template>
  <div class="wrapper">
    <Calendar v-for="month in 12">
      {{ month }}
    </Calendar>
  </div>
</template>
<style scoped>
.wrapper {
  flex-wrap: wrap;
  height: 100vh;
  display: flex;
  align-items: center;
  justify-content: center;
}
</style>
