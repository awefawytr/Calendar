<script setup>
import Empty from "./Empty.vue";

let idDay = 1;

const props = defineProps({
  countOfDay: {
    type: Number,
    required: true,
  },
  firstDay: {
    type: Number,
    required: true,
  },
});

</script>
<template>
  <Empty :firstDay="firstDay" />
  <slot v-for="number in countOfDay">
    <span class="calendar-number__day" :idDay="idDay++">{{ number }}</span>
  </slot>
</template>
<style scoped></style>