<script setup lang="ts">
import { ref } from 'vue';
import { Todo } from '../models/Todo';
import ShowTodo from './ShowTodo.vue';
import AddTodo from './AddTodo.vue';

const todos = ref<Todo[]>(JSON.parse(localStorage.getItem('todos') || '[]'));

const addTodo = (todo: string) => {
  todos.value.push(new Todo(todo, false));
  todosToLs(todos.value);
};

const toggleTodo = (i: number) => {
  todos.value[i].done = !todos.value[i].done;
  todosToLs(todos.value);
};

const removeTodo = (i: number) => {
  todos.value.splice(i, 1);
  todosToLs(todos.value);
};

function todosToLs(todos: Todo[]) {
  localStorage.setItem('todos', JSON.stringify(todos));
}
</script>

<template>
  <div class="program__container">
    <h4 class="program__container--title">Windows Todolist Program</h4>
    <div class="windowBtnContainer">
      <button class="windowBtn">
        <img
          class="windowBtnImage"
          src="../../assets/windowbuttons/win-98-minimera.png"
        />
      </button>
      <button class="windowBtn">
        <img
          class="windowBtnImage"
          src="../../assets/windowbuttons/win-98-window.png"
        />
      </button>
      <button class="windowBtn">
        <img
          class="windowBtnImage"
          src="../../assets/windowbuttons/win-98-kryss.png"
        />
      </button>
    </div>
  </div>
  <AddTodo @add-todo="addTodo"></AddTodo>
  <ShowTodo
    :todo="todo"
    v-for="(todo, index) in todos"
    :key="index"
    @toggle-todo-done="toggleTodo(index)"
    @remove-todo="removeTodo(index)"
  ></ShowTodo>
</template>

<style scoped>
.program__container {
  margin: -10px -10px 10px -10px;
  background-color: rgb(16, 0, 163);
  display: flex;
}

.program__container--title {
  padding: 7px;
  margin: 0;
  color: white;
}

.done {
  color: grey;
  text-shadow: white 1px 1px, white 0px 0px, white 1px 1px;
}

.windowBtnContainer {
  display: flex;
}

.windowBtn {
  scale: 0.8;
  background-color: #c3c3c3;
  border-top: 4px solid white;
  border-left: 4px solid white;
  border-right: 3px solid black;
  border-bottom: 3px solid black;
}

.windowBtnImage {
  width: 13px;
}
</style>
