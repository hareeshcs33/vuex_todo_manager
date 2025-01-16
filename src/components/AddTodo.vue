<template>
  <div class="add-todo">
    <form @submit="onSubmit">
      <input type="text" v-model="title" placeholder="enter todo title" />
      <input type="submit" value="submit" />
    </form>
  </div>
</template>

<script>
import { mapActions } from "vuex";

export default {
  name: "AddTodo",
  data() {
    return {
      title: "",
    };
  },
  methods: {
    ...mapActions(["addTodo"]),
    onSubmit(e) {
      e.preventDefault();
      this.addTodo(this.title);
    },
  },
};
</script>
