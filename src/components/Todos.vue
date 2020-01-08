<template>
  <div id="todo">
    <div class="todos" v-for="todo in todos" :key="todo.id">
    <v-card class="mt-4"
    sm='12'
    md='6'
    lg='4'>
      <v-container>
        <h4 class="">{{todo.name}}</h4>
        <v-btn 
        id="close"
        small 
        icon
        absolute
        right
        top
        v-on:click="() => removeTodo(todo.id)"
        ><v-icon >mdi-close</v-icon></v-btn>
      </v-container>
    </v-card>
    </div>
  </div>
</template>

<script>
export default {
  name: "Todos",
  props: ["todos"],
  methods: {
    removeTodo: function (id) {
      this.$emit("removeTodo", id)
    }
  }
}
</script>

<style>
  #close {
    margin-top: -6.8px
  }
</style>