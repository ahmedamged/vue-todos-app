<template>
  <!-- <img alt="Vue logo" src="./assets/logo.png"> -->
  <!-- <HelloWorld msg="Welcome to Your Vue.js App"/> -->
  <Header />
  <AddTodo v-on:add-todo="addTodo"/>
  <Todos v-bind:todos="todos" v-on:del-todo="deleteTodo"/>
</template>

<script>
// import HelloWorld from './components/HelloWorld.vue'
import Todos from './components/Todos.vue';
import Header from './components/layout/Header.vue';
import AddTodo from './components/AddTodo.vue';

export default {
  name: 'App',
  components: {
    Todos,
    Header,
    AddTodo
  },
  data() {
    return{
      todos: [
        {
          id: 1,
          title: "Todo One",
          completed: false
        },
        {
          id: 2,
          title: "Todo Two",
          completed: false
        },
        {
          id: 3,
          title: "Todo Three",
          completed: false
        }
      ]
    }
  },
  methods: {
    deleteTodo(id){
      this.todos = this.todos.filter(todo => todo.id !== id);
    },
    addTodo(newTodo){
      this.todos = [...this.todos, newTodo];
    }
  }
}
</script>

<style>
/* #app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
} */
  *{
    box-sizing: border-box;
    margin: 0;
    padding: 0;
  }
  body{
    font-family: Arial, Helvetica, sans-serif;
    line-height: 1.4;
  }
  .btn{
    display: inline-block;
    border: none;
    background: #555;
    color: #fff;
    padding: 7px 20px;
    cursor: pointer;
  }
  .btn:hover{
    background: #666;
  }
</style>
