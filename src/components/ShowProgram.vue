<script setup lang="ts">
import { ref } from 'vue';
import TodoList from './todo/TodoList.vue';

const isProgramActive = ref(false);
const isWindowActive = ref(false);
</script>

<template>
  <div v-show="isWindowActive" class="window">
    <div v-show="isProgramActive">
      <TodoList></TodoList>
    </div>
  </div>
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
