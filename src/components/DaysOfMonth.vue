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

let idDay = props.idDay - 1;
let countOfDay = props.countOfDay;

function giveId(){ // Функция присваивания id
  for(;idDay <= countOfDay;){
    idDay++;
    if(idDay >= 8){
      idDay = 1;
    }
    return idDay;
  }
}
</script>
<template>
  <Empty :firstDay="firstDay" />
  <slot v-for="number in countOfDay">
    <span class="calendar-number__day" :idDay="giveId()">{{ number }}</span>
  </slot>
</template>
<style scoped>
[idday^="6"], [idday^="7"]{
  color: red;
}
</style>