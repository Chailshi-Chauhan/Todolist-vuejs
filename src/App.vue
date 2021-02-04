<template>
  <div id="app">
    <div id="nav">
      <Header />
      <AddItem v-on:add-todo="addTodoItem"/>
      <Todos v-bind:todos="todos" v-on:delete-todo="deleteItem"/>
      <HelloWorld />
    </div>
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld'
import Todos from './components/Todos'
import Header from './components/Header'
import AddItem from './components/AddItem'
export default {
  name: 'App',
  components: {
    HelloWorld,
    Todos,
    Header,
    AddItem
  },
  data () {
    return {
      todos: [{
        msg: 'first',
        number: 1,
        isCompleted: false
      },
      {
        msg: 'second',
        number: 2,
        isCompleted: false
      },
      {
        msg: 'third',
        number: 3,
        isCompleted: false
      }
      ]
    }
  },
  methods: {
    deleteItem (number) {
      console.log('inside delete')
      this.todos = this.todos.filter(todo => todo.number !== number)
    },
    addTodoItem (newItem) {
      console.log('inside adding item')
      this.todos = [...this.todos, newItem]
    }
  }
}
</script>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

#nav {
  padding: 30px;

  a {
    font-weight: bold;
    color: #2c3e50;

    &.router-link-exact-active {
      color: #42b983;
    }
  }
}
</style>
