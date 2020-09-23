<template>
  <div id="app">
    <h1>Todo List with Vuejs</h1>
    <TodoInput @addTodo="addTodo($event)" />

    <TodoList :todos="todos"/>
  </div>
</template>

<script>
import TodoList from './components/TodoList.vue'
import TodoInput from './components/TodoInput.vue'

export default {
  name: 'App',
  components: {
    TodoList,
    TodoInput
  },
  data() {
    return {
      
      todos : [
        {
          title : 'workout',
          done : false 
        },
        {
          title : 'read book',
          done : true 
        },
        {
          title : 'study',
          done : false 
        },
        {
          title : 'sleep',
          done : false 
        }
      ]
    }
  },
  methods: {
    addTodo(payload){
      console.log(payload)
      const newTodo = {
        title : payload,
        done : false 
      }
      this.todos.push(newTodo)
      console.log(newTodo)
    }
  },
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  max-width: 500px;
  margin: 0 auto;
  margin-top: 60px;
  

}
</style>
