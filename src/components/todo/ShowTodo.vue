<script setup lang="ts">
import { Todo } from '../models/Todo';

interface ITodo {
  todo: Todo;
}
defineProps<ITodo>();
const emit = defineEmits(['toggleTodoDone', 'removeTodo']);
</script>

<template>
  <div @click="() => emit('toggleTodoDone')" class="todosContainer">
    <div class="todosContainer" :class="todo.done ? 'done' : ''">
      <input class="checkbox" type="checkbox" :checked="todo.done" />
      <p class="todos">{{ todo.todo }}</p>
    </div>
    <button class="removeBtn" @click="() => emit('removeTodo')">
      <img src="../../assets/windowbuttons/win-98-kryss.png" />
    </button>
  </div>
</template>

<style scoped>
.todosContainer {
  display: flex;
  flex-direction: row;
  justify-content: space-between;
}

.removeBtn {
  background-color: rgba(0, 0, 0, 0);
  border-style: none;
  scale: 0.8;
}

.todos {
  margin: 8px;
}
.checkbox {
  accent-color: grey;
}
</style>
