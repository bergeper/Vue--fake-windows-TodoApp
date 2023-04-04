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

<style scoped>
.date {
  position: fixed;
  right: 0;
  margin: 0 10px 0 0;
  padding: 2px;
  border-left: solid black 2px;
  border-top: solid black 2px;
  border-right: solid white 2px;
  border-bottom: solid white 2px;
  font-size: 20px;
  font-family: sans-serif;
}
</style>
