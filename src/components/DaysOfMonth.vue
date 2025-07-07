<script setup>
import Empty from "./Empty.vue";

const props = defineProps({
  countOfDay: {
    type: Number,
    required: true,
  },
  firstDay: {
    type: Number,
    required: true,
  },
  idDay: {
    type: Number,
    required: true
  }
});

function giveId(){
  for(let idDay = props.idDay; idDay < props.firstDay; idDay++){
    console.log(idDay);
  }
}
giveId();
</script>
<template>
  <Empty :firstDay="firstDay" />
  <slot v-for="number in countOfDay">
    <span class="calendar-number__day" :idDay="giveId()">{{ number }}</span>
  </slot>
</template>
<style scoped></style>