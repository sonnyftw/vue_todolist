<template>
  <div class="todo-item" v-bind:class="{'is-complete':todoi.completed}">
    <p>
      <input type="checkbox" v-on:change="markComplete">
      {{todoi.title}}
      <button @click="$emit('del-todo', todoi.id)" class="del">x</button>
    </p>
  </div>
</template>

<script>
export default {
  name: "TodoItemTemplate",
  props: ["todoi"],
  methods: {
    markComplete() {
      this.todoi.completed = !this.todoi.completed;
    }
  }
}
</script>

<style scoped>
  .todo-item {
    background: #f4f4f4;
    padding: 10px;
    border-bottom: 1px #ccc dotted;
  }
  .is-complete {
    text-decoration: line-through;
  }
  .del {
    background: #ff0000;
    color: #fff;
    border: none;
    padding: 5px 9px;
    border-radius: 50%;
    cursor: pointer;
    float: right;
  }  
</style>