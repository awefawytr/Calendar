<script setup>
  const props = defineProps({
    firstDay: {
      type: Number,
      required: true,
    },
  });

  // console.log(props.firstDay);
</script>

<template>
  <div class="empty" v-for="empty in firstDay - 1"></div>
</template>