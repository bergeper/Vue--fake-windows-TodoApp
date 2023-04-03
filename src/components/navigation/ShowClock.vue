<script setup lang="ts">
const updateTime = (): string => {
  let date: Date = new Date();
  let currentTime =
    date.getHours() + ':' + date.getMinutes() + ':' + date.getSeconds();
  let showTime = currentTime.toString();
  return showTime;
};

setInterval(updateTime, 1000);
let showTime = updateTime();
console.log(showTime);
</script>

<template>
  <span id="date" class="date">
    {{ (showTime = updateTime()) }}
  </span>
</template>
