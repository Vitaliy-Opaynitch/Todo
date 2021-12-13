<template>
  <div>
    <!-- <h2>Todo App from Vitalii Opaynitch</h2> -->
    <router-link to="/" class="link">Home</router-link>
    <AddDo v-on:add-todo="addTodo" />
    <Todolist v-bind:todos="todos" v-on:remove-todo="removeTodo" />
  </div>
</template>
<script>
import Todolist from "@/components/Todolist";
import AddDo from "@/components/AddDo";
export default {
  name: "App",
  data() {
    return {
      todos: [
        // { id: 1, title: "Learn JS", completed: false },
        // { id: 2, title: "Learn Vue JS", completed: false },
        // { id: 3, title: "Learn React JS", completed: false },
        // { id: 4, title: "Learn Angular JS", completed: false },
      ],
    };
  },
  mounted() {
    fetch("https://jsonplaceholder.typicode.com/todos?_limit=12")
      .then((response) => response.json())
      .then((json) => {
        this.todos = json;
      });
  },
  methods: {
    removeTodo(id) {
      this.todos = this.todos.filter((t) => t.id !== id);
    },
    addTodo(todo) {
      this.todos.push(todo);
    },
  },
  components: {
    Todolist,
    AddDo,
  },
};
</script>

<style scoped>
</style>