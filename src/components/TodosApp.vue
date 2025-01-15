<template>
  <div class="todos">
    <div
      @dblclick="onDblclick(todo)"
      class="todo"
      :class="todo.completed ? 'todo-completed' : 'todo-incomplete'"
      v-for="todo in allTodos"
      :key="todo.id"
    >
      <p>{{ todo.title }}</p>
      <button @click="deleteTodo(todo.id)">Delete</button>
    </div>
  </div>
</template>

<script>
import { mapGetters, mapActions } from "vuex";

export default {
  name: "TodosApp",
  methods: {
    ...mapActions(["fetchTodos", "deleteTodo", "updateTodo"]),
    onDblclick(todo) {
      const updTodo = {
        id: todo.id,
        title: todo.title,
        completed: !todo.completed,
      };
      this.updateTodo(updTodo);
    },
  },
  computed: mapGetters(["allTodos"]),
  created() {
    this.fetchTodos();
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.todos {
  display: flex;
  flex-flow: row wrap;
}
.todo {
  width: 30%;
  border: 1px solid black;
  padding: 10px;
  margin: 10px;
}
.todo-completed {
  background-color: #42b983;
  color: #fff;
}
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
