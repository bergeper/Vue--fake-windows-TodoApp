<script setup lang="ts">
import { ref } from 'vue';

const time = ref('');

setInterval(() => {
  const date: Date = new Date();
  const currentTime =
    date.getHours() + ':' + date.getMinutes() + ':' + date.getSeconds();
  time.value = currentTime.toString();
}, 1000);
</script>

<template>
  <span id="date" class="date">
    {{ time }}
  </span>
</template>
