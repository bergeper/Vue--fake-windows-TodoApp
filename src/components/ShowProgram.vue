<script setup lang="ts">
import { ref } from 'vue';
import TodoList from './todo/TodoList.vue';
import OpenMenu from './navigation/OpenMenu.vue';

const isWindowActive = ref(true);
const isProgramActive = ref(false);

const openProgram = () => {
  if (isProgramActive.value) {
    isProgramActive.value = false;
    isWindowActive.value = false;
  } else {
    isProgramActive.value = true;
    isWindowActive.value = true;
  }
};
</script>

<template>
  <div v-show="isWindowActive" class="window">
    <TodoList v-if="isProgramActive"></TodoList>
  </div>
  <OpenMenu @todo-app="openProgram"></OpenMenu>
</template>

<style scoped>
.window {
  background-color: #c3c3c3;
  border-top: 4px solid white;
  border-left: 4px solid white;
  border-right: 3px solid black;
  border-bottom: 3px solid black;
  padding: 10px;
}
</style>
