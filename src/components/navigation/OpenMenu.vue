<script setup lang="ts">
import ShowClock from './ShowClock.vue';
let show = false;

const showMenu = () => {
  show = true;
};
</script>

<template>
  <div v-show="show" id="menu" class="menu">
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
  <button @click.prevent="showMenu" class="program__btn">
    <img src="../../assets/win-98-logo.png" class="program__btn--logo" />
    Start
  </button>
  <ShowClock />
</template>
