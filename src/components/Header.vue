<template>
  <div id="header">
    <v-card>
      <v-container>

            <v-text-field
            filled
            label="Enter New Todo"
            v-model="todoValue"
            ></v-text-field>

            <v-btn depressed right
            v-on:click="$emit('createTodo', todoValue, todoValue='' )"
            >New Todo<v-icon>mdi-plus</v-icon></v-btn>  
      </v-container>
    </v-card>
  </div>
    
    
</template>

<script>
export default {
  data: ()=> {
    return {
      todoValue: ''
    }
  }
}; 


</script>

<style lang="scss" scoped>
  #header {
    margin-top: 70px;
  }
</style>
