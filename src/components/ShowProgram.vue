<script setup lang="ts">
import { ref } from 'vue';
import TodoList from './todo/TodoList.vue';
import OpenMenu from './navigation/OpenMenu.vue';
import OmdbSearch from './omdb/OmdbSearch.vue';
import ShowMaxIcons from './maxicons/ShowMaxIcons.vue';

const isWindowActive = ref(false);
const isTodoActive = ref(false);
const isOmdbActive = ref(false);
const isMaxIconsActive = ref(false);

const openTodoApp = (isActive: boolean) => {
  if (isActive && isTodoActive.value) {
    isTodoActive.value = false;
    isWindowActive.value = false;
  } else {
    isTodoActive.value = true;
    isWindowActive.value = true;
  }
};
</script>

<template>
  <div v-show="isWindowActive" class="window">
    <TodoList v-if="isTodoActive"></TodoList>
    <OmdbSearch v-if="isOmdbActive"></OmdbSearch>
    <ShowMaxIcons v-if="isMaxIconsActive"></ShowMaxIcons>
  </div>
  <OpenMenu
    @omdb="openTodoApp(isOmdbActive)"
    @max-icons="openTodoApp(isMaxIconsActive)"
    @todo-app="openTodoApp(isTodoActive)"
  ></OpenMenu>
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
