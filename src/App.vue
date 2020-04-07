<template>
  <div id="app">
    <to-do-list v-bind:todos="todos"></to-do-list>
    <create-to-do v-on:create-todo="addToDo"></create-to-do>
  </div>
</template>

<script>
import ToDoList from './components/ToDoList/'
import CreateToDo from './components/ToDoList/CreateToDo'

export default {
  name: 'App',
  components: {
    ToDoList,
    CreateToDo
  },
  data () {
    return {
      todos: [
        {
          title: 'Todo A',
          project: 'Project A',
          done: false
        },
        {
          title: 'Todo B',
          project: 'Project B',
          done: true
        },
        {
          title: 'Todo C',
          project: 'Project C',
          done: false
        },
        {
          title: 'Todo D',
          project: 'Project D',
          done: false
        }
      ]

    }
  },
  methods: {
    addToDo (toDoItem) {
      this.todos.push(toDoItem)
    }
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
