<script setup>
  // Необходимо получить с какого дня начинается месяц и от него отталкиваться
  const props = defineProps({
    firstDay: {
      type: Number,
      required: true,
    },
  });

  console.log(props.firstDay);
</script>

<template>
  <div class="empty" v-for="empty in firstDay - 1"></div>
</template>