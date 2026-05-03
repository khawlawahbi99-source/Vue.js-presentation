<template>
  <div class="app-container">
    <h1>Ma Todo List</h1>
    <TodoList />
  </div>
</template>

<script>
import TodoList from './components/TodoList.vue'

export default {
  name: 'App',
  components: { TodoList }
}
</script>

<style>
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

body {
  background-color: #f0f2f5;
  font-family: Arial, sans-serif;
}

.app-container {
  max-width: 500px;
  margin: 40px auto;
  padding: 0 16px;
}

h1 {
  text-align: center;
  margin-bottom: 24px;
  color: #2c3e50;
}
</style>