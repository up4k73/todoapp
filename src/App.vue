<template>
  <v-app dark>
    <h1>Todo app</h1>
    <AddTodo
        @add-todo="addTodo"
    />
    <TodoList
            v-bind:todos="todos"
            @remove-todo="removeTodo"
    />
  </v-app>
</template>

<script>
import TodoList from '@/components/TodoList'
import AddTodo from '@/components/AddTodo'
export default {
  name: 'App',
  data(){
    return {
      todos: [
        {id: 1, title: 'купить хлеб', completed: false, editable: true}
      ]
    }
  },
  methods: {
    removeTodo(id){
      this.todos = this.todos.filter(t => t.id !== id)
  },
    addTodo(todo) {
      this.todos.push(todo)
    }
  },
  components: {
    TodoList, AddTodo
  },
}
</script>
<style v-app>
  #app {
    font-family: Roboto, sans-serif;
    text-align: center;
    margin-top: 30px;
    margin-left: 30%;
    margin-right: 30%;
    justify-content: center;
    }
</style>