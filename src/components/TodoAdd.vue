<template>
  <div class="w-100 d-flex justify-content-center align-items-center">
    <input type="text" class="w-50" v-model="todoName" v-on:keyup.enter="submit" />
  </div>
</template>

<script>
export default {
  name: "TodoAdd",
  data: function() {
    return {
      todoName: ""
    };
  },
  methods: {
    submit() {
      this.$emit("addTodo", this.todoName);
      this.todoName = "";
    }
  }
};
</script>

<style>
.w-100 {
  width: 100%;
}
.d-flex {
  display: flex;
}
.justify-content-center {
  justify-content: center;
}
.align-items-center {
  align-items: center;
}
</style>
