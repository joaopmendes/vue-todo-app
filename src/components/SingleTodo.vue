<template>
  <div
    v-bind:class="{
      todo: true,
      'is-completed': todo.completed,
      'w-100': true,
      'd-flex': true,
      'justify-content-center': true,
      'py-2': true,
      'my-2': true,
      'align-items-center': true
    }"
  >
    <input type="checkbox" @change="$emit('toggleTodo', todo.id)" />
    <p>{{ todo.title }}</p>
    <button @click="$emit('deleteTodo', todo.id)" class="btn btn-primary">Remover</button>
  </div>
</template>

<script>
export default {
  name: "SingleTodo",
  props: ["todo"]
};
</script>

<style>
p {
  text-align: center;
}
.my-2 {
  margin-top: 8px;
  margin-bottom: 8px;
}
.py-2 {
  padding-top: 8px;
  padding-bottom: 8px;
}
.is-completed {
  color: green;
  text-decoration: line-through;
}

.todo p {
  margin: 0px 30px;
}
</style>
