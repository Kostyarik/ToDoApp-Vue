<template>
  <div>
    <to-do-item v-on:complete-todo="completeToDo" v-on:delete-todo="deleteTodo" v-for="todo in todos" v-bind:todo="todo"></to-do-item>
  </div>
</template>

<script type = "text/javascript" >
import ToDoItem from './ToDoItem/'
export default {
  name: 'ToDoList',
  props: ['todos'],
  components: {ToDoItem},
  methods: {
    deleteTodo (todo) {
      const todoIndex = this.todos.indexOf(todo)
      this.todos.splice(todoIndex, 1)
    },
    completeToDo (todo) {
      const todoIndex = this.todos.indexOf(todo)
      this.todos[todoIndex].done = true
    }
  }
}
</script>
<style>
</style>
