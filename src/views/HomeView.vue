<template>
  <div class="home">
    <AddTodo />
    <FilterTodos />
    <TodosApp />
  </div>
</template>

<script>
// @ is an alias to /src
import AddTodo from "@/components/AddTodo.vue";
import TodosApp from "@/components/TodosApp.vue";
import FilterTodos from "@/components/FilterTodos.vue";

export default {
  name: "HomeView",
  components: {
    TodosApp,
    AddTodo,
    FilterTodos,
  },
};
</script>
