<template>
  <div id="app">
    <h1>To do list</h1>
    <AddTodo
    @add-todo='addTodo'
    />
    <hr>
    <TodoList
     v-bind:todos='todos'
     @remove-todo='removeTodo'
    />
  </div>
</template>

<script>
import AddTodo from '@/components/AddTodo'
import TodoList from '@/components/TodoList'
export default {
  name: 'App',
  data() {
    return {
      todos: []
    }
  },
  components: {
    TodoList, AddTodo
  },
  methods: {
    removeTodo(id) {
      this.todos = this.todos.filter(t => t.id !== id)
    },
    addTodo(todo) {
      this.todos.push(todo)
    }
  }
}
</script>

<style>
</style>
