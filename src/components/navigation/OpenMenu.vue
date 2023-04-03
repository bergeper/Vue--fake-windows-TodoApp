<script setup lang="ts">
import { ref } from 'vue';
import ShowClock from './ShowClock.vue';

const isActive = ref(false);

const showMenus = () => {
  if (isActive.value) {
    isActive.value = false;
  } else {
    isActive.value = true;
  }
};
</script>

<template>
  <div v-if="isActive" class="menu">
    <button class="menuBtn">
      <img src="../../assets/win-98-notepad.png" class="menuBtn__logo" />Todo
    </button>

    <button class="menuBtn" id="omdbBtn">
      <img src="../../assets/win-98-media-player.png" class="menuBtn__logo" />
      Search For Movies
    </button>

    <button class="menuBtn">
      <img src="../../assets/folder-win-98.png" class="menuBtn__logo" />
      Max Icons
    </button>
  </div>
  <button @click="showMenus" class="program__btn">
    <img src="../../assets/win-98-logo.png" class="program__btn--logo" />
    Start
  </button>
  <ShowClock />
</template>
