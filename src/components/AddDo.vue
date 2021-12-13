<template>
  <form v-on:submit.prevent="onSubmit">
    <input type="text" v-model="title" />
    <button type="submit">Add Do</button>
  </form>
</template>

<script>
export default {
  data() {
    return {
      title: "",
    };
  },
  methods: {
    onSubmit() {
      if (this.title.trim()) {
        let newTodo = {
          id: Date.now(),
          title: this.title,
          completed: false,
        };
        this.$emit("add-todo", newTodo);
        this.title = "";
      }
    },
  },
};
</script>

<style scoped>
form {
  display: flex;
  justify-content: center;
  margin: 20px 0;
}
input {
  border: none;
  outline: none;
  margin-right: 20px;
  padding: 5px;
  border-radius: 5px;
  width: 250px;
}
button {
  border: none;
  background-color: #136366;
  color: #fff;
  border-radius: 15px;
  transition: 0.3s;
  cursor: pointer;
  width: 80px;
  user-select: none;
  padding: 0 10px;
  text-transform: uppercase;
  border: 1px solid #fff;
}
button:hover {
  border-radius: 5px;
}
</style>