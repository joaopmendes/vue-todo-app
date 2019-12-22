<template>
  <div>
    <div v-for="todo in todos" :key="todo.id">
      <SingleTodo v-bind:todo="todo" @deleteTodo="deleteTodo" @toggleTodo="toggleTodo" />
    </div>
  </div>
</template>

<script>
import SingleTodo from "./SingleTodo";
export default {
  components: {
    SingleTodo
  },
  name: "TodoList",
  props: ["todos"],
  created() {},
  methods: {
    deleteTodo(id) {
      this.$emit("deleteTodo", id);
    },
    toggleTodo(id) {
      this.$emit("toggleTodo", id);
    }
  }
};
</script>