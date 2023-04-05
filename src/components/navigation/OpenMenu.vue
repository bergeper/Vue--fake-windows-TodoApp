<script setup lang="ts">
import { ref } from 'vue';
import ShowClock from './ShowClock.vue';

const isActive = ref(false);

const showMenu = () => {
  if (isActive.value) {
    isActive.value = false;
  } else {
    isActive.value = true;
  }
};

const emit = defineEmits(['todoApp', 'omdb', 'maxIcons']);
</script>

<template>
  <div v-show="isActive" class="menu">
    <button @click="emit('todoApp')" class="menuBtn">
      <img src="../../assets/win-98-notepad.png" class="menuBtn__logo" />Todo
    </button>

    <button @click="emit('omdb')" class="menuBtn" id="omdbBtn">
      <img src="../../assets/win-98-media-player.png" class="menuBtn__logo" />
      Search For Movies
    </button>

    <button @click="emit('maxIcons')" class="menuBtn">
      <img src="../../assets/folder-win-98.png" class="menuBtn__logo" />
      Max Icons
    </button>
  </div>
  <nav class="nav">
    <button @click="showMenu" class="program__btn">
      <img src="../../assets/win-98-logo.png" class="program__btn--logo" />
      Start
    </button>
    <ShowClock></ShowClock>
  </nav>
</template>

<style scoped>
.program__btn {
  background-color: #c3c3c3;
  margin: 0 0 0 5px;
  font-family: sans-serif;
  font-weight: bolder;
  border-top: 4px solid white;
  border-left: 4px solid white;
  border-right: 3px solid black;
  border-bottom: 3px solid black;
}
.program__btn:active {
  border-top: 4px solid black;
  border-left: 4px solid black;
  border-right: 3px solid white;
  border-bottom: 3px solid white;
}
.program__btn--logo {
  width: 25px;
}

.menu {
  display: flex;
  flex-direction: column;
  width: 35%;
  background-color: #c3c3c3;
  border-top: 4px solid white;
  border-right: 3px solid black;
  position: fixed;
  bottom: 38px;
  left: 0;
}

.menuBtn {
  display: block;
  left: 0;
  background-color: rgba(255, 255, 255, 0);
  display: flex;
  flex-direction: row;
  align-items: center;
  margin: 5px;
  border: none;
}
.menuBtn:hover {
  background-color: rgb(16, 0, 163);
  color: white;
}
.menuBtn__logo {
  width: 35px;
}
.nav {
  border-top: 4px solid rgba(255, 255, 255, 0.904);
  background-color: #c3c3c3;
  width: 100%;
  position: fixed;
  bottom: 0;
  left: 0;
}
</style>
