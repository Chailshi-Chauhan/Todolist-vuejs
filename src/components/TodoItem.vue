<template>
  <div class="todo_item" v-bind:class="{'is-completed':todo.isCompleted}">
    <h1>
      <input type="checkbox" v-on:change="marked">
      {{ todo.msg }}</h1>
      <button @click="$emit('delete-todo',todo.number)"  class="delete">X</button>
  </div>
</template>

<script>
export default {
  name: 'TodoItem',
  props: [
    'todo'
  ],
  methods: {
    marked () {
      console.log('Inside marked')
      this.todo.isCompleted = !this.todo.isCompleted
    }
  }
}
</script>

<style scoped>
.todo-item {
    background: #da282804;
    padding: 10px;
    border-bottom: 1px #ccc dotted;
  }
  .is-completed{
    text-decoration: line-through;
  }
  .delete{
    background: red;
    border-radius: 50%;
  }
</style>
