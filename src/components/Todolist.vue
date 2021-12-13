<template>
  <div>
    <ul>
      <Listitem
        v-for="(todo, i) of todos"
        v-bind:todo="todo"
        v-bind:index="i"
        v-on:remove-todo="removeTodo"
      />
    </ul>
  </div>
</template>

<script>
import Listitem from "@/components/Listitem";
export default {
  props: ["todos"],
  components: {
    Listitem,
  },
  methods: {
    removeTodo(id) {
      this.$emit("remove-todo", id);
    },
  },
};
</script>
<style scoped>
ul {
  padding: 0;
  margin: 0;
}
</style>