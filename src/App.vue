<template>
  <div id="app">
    <create-todo v-on:create-todo='createTodo'></create-todo>
    <h3>Todo List:</h3>
    <ul>
      <todo-list v-for="todo in todos" v-bind:item="todo"></todo-list>
    </ul>
  </div>
</template>

<script>
import TodoList from "./components/TodoList";
import CreateTodo from './components/CreateTodo';

export default {
  name: "App",
  components: {
    TodoList,
    CreateTodo
  },
  data() {
    return {
      todos: [],
      todo: ''
    };
  },
  methods: {
    createTodo(todo) {
      this.todos.push({todo:todo, done:false})
    }
  }
};
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
}
</style>
