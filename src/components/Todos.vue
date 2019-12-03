<template>
  <div>
    <div v-for="todo in todos" v-bind:key="todo.id">
      <!-- <h1>{{todo.id}}</h1> -->
      <TodoItem v-bind:todo="todo"/>
    </div>
  </div>

</template>


<script>
import TodoItem from "./TodoItem";

export default {
name: "Todos",
props: ["todos"],
components: {
  TodoItem
}
}

</script>

<style scoped>

</style>
