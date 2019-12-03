<template>
  <div id="app">
    <HelloWorld msg="Welcome to Your Vue.js App"/>
    <Todos v-bind:todos="todos" v-on:del-todo="deleteTodo"/>
    <AddTodo v-on:add-to="addTodo"/>
    <!-- <h1>{{msg}}</h1>  -->
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
import Todos from './components/Todos';
import AddTodo from "./components/AddTodo";

export default {
  name: 'app',
  components: {
    HelloWorld, Todos, AddTodo
  },
  data() {
    return {
      todos: [
        {
          id: 1,
          title: "TODO ONE",
          completed: false
        },
        {
          id: 2,
          title: "TODO TWO",
          completed: true
        },
        {
          id: 3,
          title: "TODO Three",
          completed: false
        }
      ],
      msg: "Hello"
    }
  },
  methods: {
      deleteTodo(id) {
      this.todos = this.todos.filter(todo => {
        return todo.id !== id;
      })
    },
    addTodo(todo) {
      this.todos = [...this.todos, todo];
    }
  }
}
</script>

<style>
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

body {
  font-family: Arial, Helvetica, sans-serif;
  line-height: 1.4;
}
</style>
