<script setup lang="ts">
import { ref } from 'vue';

const todo = ref('');
const emit = defineEmits(['addTodo']);

const clearInput = () => {};
</script>

<template>
  <form class="form" @submit.prevent="emit('addTodo', todo), clearInput">
    <input
      class="form__input"
      v-model="todo"
      placeholder="Whatya need to be doin"
      type="text"
    />
    <button class="form__btn">Save</button>
  </form>
</template>

<style scoped>
.form__input {
  border-top: 2px solid black;
  border-left: 2px solid black;
  border-right: 1px solid white;
  border-bottom: 1px solid white;
}

.form__btn {
  background-color: #c3c3c3;
  margin: 0 0 0 5px;
  font-family: sans-serif;
  font-weight: bolder;
  border-top: 2px solid white;
  border-left: 2px solid white;
  border-right: 1px solid black;
  border-bottom: 1px solid black;
}
</style>
