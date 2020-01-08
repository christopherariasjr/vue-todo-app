<template>
  <v-app>
    <v-app-bar app>
      <v-title>Todo Vue</v-title>
    </v-app-bar>

    <v-card-text>
      <v-container>
        <Header id="header" v-on:createTodo="createTodo"></Header>
        <Todos v-bind:todos="todos" v-on:removeTodo="removeTodo"></Todos>
      </v-container>
    </v-card-text>
  </v-app>
</template>

<script>
import Header from './components/Header'
import Todos from './components/Todos'

let todos = []

export default {
  name: "App",

  components: {
    Header,
    Todos,
  },

  data: () => {
    return{
      todos: todos
    }
  },
  methods: {
    createTodo(todo) {
      let todosObject = {
        id: Math.floor(Math.random() * 10),
        name: todo,
        done: false,
      }

      this.todos.push(todosObject)
    },
    removeTodo: function(id) {
      this.todos = this.todos.filter(todo => todo.id != id);

    }
  }
};
</script>

