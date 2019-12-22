<template>
  <div>
    <div id="app">
      <img alt="Vue logo" src="./assets/logo.png" />
    </div>
    <div>
      <TodoAdd v-on:addTodo="addTodo" />
      <TodoList v-bind:todos="todos" @toggleTodo="toggleTodo" @deleteTodo="deleteTodo" />
    </div>
  </div>
</template>

<script>
import TodoList from "./components/TodoList.vue";
import TodoAdd from "./components/TodoAdd.vue";
export default {
  name: "app",
  components: {
    TodoList,
    TodoAdd
  },
  data: () => ({
    todos: []
  }),
  methods: {
    deleteTodo(id) {
      this.todos = this.todos.filter(todo => todo.id !== id);
      //eslint-disable-next-line no-console
      console.log("I got called with id of" + id);
    },
    addTodo(title) {
      this.todos.push({
        id: Math.floor(Math.random() * 10000),
        title,
        completed: false
      });
    },
    toggleTodo(id) {
      this.todos = this.todos.map(todo => {
        todo.id === id && (todo.completed = !todo.completed);

        return todo;
      });
    }
  }
};
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
