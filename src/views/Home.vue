<template>
  <div id="app">
    <!-- <Header /> -->
    <AddTodo v-on:add-todo="addTodo" />
    <Todostemplate v-bind:todosdata="todosdata" v-on:del-todo="deleteTodo" />
  </div>
</template>

<script>
// import Header from '../components/layout/Header';
import Todostemplate from '../components/Todos';
import AddTodo from '../components/AddTodo';
import axios from 'axios';

export default {
  name: 'Home',
  components: {
    // Header,
    Todostemplate,
    AddTodo
  },
  data() {
    return {
      todosdata: [
        // {
        //   id: 1,
        //   title: "Todo One",
        //   completed: false
        // },
        // {
        //   id: 2,
        //   title: "Todo Two",
        //   completed: true
        // },
        // {
        //   id: 3,
        //   title: "Todo Three",
        //   completed: false
        // }
      ]
    }
  },
  methods: {
    deleteTodo(id) {
      axios.delete(`https://jsonplaceholder.typicode.com/todos/${id}`)
      .then(res => this.todosdata = this.todosdata.filter(todoi => todoi.id !== id))
      .catch(err => console.log(err));
    },
    addTodo(newTodo) {
      const { title, completed} = newTodo;
      axios.post('https://jsonplaceholder.typicode.com/todos', {
        title,
        completed
      })
      .then(res => this.todosdata = [...this.todosdata, res.data])
      .catch(err => console.log(err));  
    } 
  },
  created() {
    axios.get('https://jsonplaceholder.typicode.com/todos?_limit=5')
      .then(res => this.todosdata = res.data)
      .catch(err => console.log(err));

  }
}
</script>

<style>
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

body {
  font-family: Arial, Helvetica, sans-serif;
  line-height: 1.4;
}

.btn {
  display: inline-block;
  border: none;
  background: #555;
  color: #fff;
  padding: 7px 20px;
  cursor: pointer;
}

.btn:hover {
  background: #666;
}
</style>
