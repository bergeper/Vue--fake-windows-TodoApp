<script setup lang="ts">
import OpenMenu from './OpenMenu.vue';
</script>

<template>
  <div class="nav">
    <OpenMenu></OpenMenu>
  </div>
</template>

<style scoped>
.nav {
  background-color: #c3c3c3;
  width: 100%;
  position: fixed;
  bottom: 0;
  border-top: 4px solid rgba(255, 255, 255, 0.904);
}
</style>
