<template id="">
  <div class="todo-item" v-bind:class="{'is-complete':todoI.completed}">
    <h2>
      <input type="checkbox" v-on:change="markComplete">
      {{todo.title}}
    </h2>
  </div>
</template>

<script>
  export default{
    name: "TodoItem",
    props: ["todo"],
    data() {
       return {
          todoI: this.todo
       }
    },
    methods:{
      markComplete(){
        this.todoI.completed = !this.todoI.completed
      }
    }
  }
</script>

<style scoped>
    .todo-item{
      background: #f4f4f4;
      padding: 10px;
      border-bottom: 1px #ccc dotted;
    }
    .is-complete{
      text-decoration: line-through;
    }
    .del{

    }
</style>
