<template>
  <div>
    <div v-bind:key="todosfor.id" v-for="todosfor in todosdata">
      <TodoItemTemplate v-bind:todoi="todosfor" v-on:del-todo="$emit('del-todo', todosfor.id)"/>
    </div>  
  </div> 
</template>

<script>
import TodoItemTemplate from './Todoitem.vue';

export default {
  name: "Todostemplate",
  components: {
    TodoItemTemplate
  },
  props: ["todosdata"]
}
</script>

<style scoped>
  
</style>