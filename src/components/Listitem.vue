<template>
  <li>
    <span v-bind:class="{ through: todo.completed }">
      <input type="checkbox" v-on:change="todo.completed = !todo.completed" />
      <span>{{ index + 1 }}</span>
      {{ todo.title }}
    </span>
    <button class="btn-close" v-on:click="$emit('remove-todo', todo.id)">
      &times;
    </button>
  </li>
</template>

<script>
export default {
  props: {
    todo: {
      type: Object,
      required: true,
    },
    index: Number,
  },
};
</script>

<style scoped>
li {
  padding: 5px;
  margin: 0 auto;
  display: flex;
  justify-content: space-between;
  text-align: center;
  max-width: 550px;
  color: #064206;
  font-size: 16px;
}
input,
span {
  margin-right: 10px;
}
.btn-close {
  border: none;
  outline: none;
  background-color: #14585a;
  border: 1px solid #fff;
  border-radius: 50%;
  color: #fff;
  font-size: 15px;
  cursor: pointer;
  transition: 0.4s;
}
.btn-close:hover {
  transform: rotate(95deg);
}
.through {
  text-decoration: line-through;
}
</style>