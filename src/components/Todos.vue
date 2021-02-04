<template>
  <div>
    <div v-for='todo in todos' :key='todo.number'>
      <TodoItem v-bind:todo='todo' v-on:delete-todo="$emit('delete-todo',todo.number)"/>
    </div>
  </div>
</template>

<script>
import TodoItem from './TodoItem'
export default {
  name: 'Todos',
  components: {
    TodoItem
  },
  props: ['todos']
}
</script>

<style scoped>
</style>
