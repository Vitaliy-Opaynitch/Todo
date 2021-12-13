<template>
  <div id="app">
    <h1>Todo App from Vitalii Opaynitch</h1>
    <br />
    <!-- <AddDo v-on:add-todo="addTodo" />
    <Todolist v-bind:todos="todos" v-on:remove-todo="removeTodo" /> -->
    <router-view />
  </div>
</template>

// <script>
</script>

<style>
body {
  height: 100vh;
  background: linear-gradient(#414d59, #b1bfc1) no-repeat;
  overflow: hidden;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #167add;
  margin-top: 10px;
}
h1 {
  font-size: 24px;
  padding-bottom: 10px;
  color: #2b87dd;
  border-bottom: 1px solid #0ad60a;
}
ul {
  list-style: none;
  user-select: none;
}
a {
  text-decoration: none;
  color: #cccccc;
  transition: 0.3s;
}
a:hover {
  color: #ffffff;
}
</style>
