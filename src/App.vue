import TodoList from './Components/TodoList'

<template>
  <div id="app">
    <TodoList v-bind:todos="todos"></TodoList>
    <CreateTodo v-on:create-todo="createTodo"></CreateTodo>
  </div>
</template>

<script>
import TodoList from "./components/TodoList";
import CreateTodo from "./components/CreateTodo";
export default {
  name: "App",
  components: {
    TodoList,
    CreateTodo,
  },
  data() {
    return {
      todos: [
        {
          title: "标题",
          project: "代办事项",
          done: false
        },
        {
          title: "标题二",
          project: "代办事项二",
          done: true
        },
      ],
    };
  },
  methods:{
    createTodo(data){
      this.todos.push({
        title:data.title,
        project:data.project,
        done:false,
      });
    },
  },
};
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
