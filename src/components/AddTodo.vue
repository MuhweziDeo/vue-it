<template id="">
<form @submit="addTodo" >
  <input type="text" name="" v-model="title" placeholder="Add Todo...">
  <input type="submit" name="" value="Submit">
</form>
</template>

<script>
export default {
  name: "AddTodo",
  data(){
    return {
      title: ''
    }
  }
  methods: {
    addTodo(e) {
      e.preventDefault();
      const todo = {
        id: Math.random(),
        title: this.title,
        completed: false
      }
      this.$emit('add-todo', todo);
      this.title = '';
    }
  }
}
</script>
