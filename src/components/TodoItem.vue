<template>
  <div class="">
    <p>{{todo.id}}</p>
    <p v-bind:class="{'is-complete': todo.completed}"><input type="checkbox" v-on:change="markComplete">{{todo.title}}</p>
    <button type="button" @click="$emit('del-todo', todo.id)" name="button">Delete</button>
  </div>

</template>

<script type="text/javascript">
export default {
  name: "todoItem",
  props: ["todo"],
  methods: {
    markComplete() {
      this.todo.completed = !this.todo.completed;
    }
  }

}
</script>


<style scoped>
.is-complete {
  text-decoration: line-through;
}

</style>
