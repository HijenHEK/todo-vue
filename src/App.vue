<template>
  <div id="app">
    <h1>Todo List with Vuejs</h1>
    <TodoInput @addTodo="addTodo($event)" />

    <TodoList :todos="todos" @todo-done="todoDone($event)" @del-todo="delTodo($event)"/>
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
          details : 'lorem lorem ,aknfkankanklnanklanflk' ,
          done : false 
        },
        {
          title : 'read book',
          details : 'lorem lorem ,aknfkankanklnanklanflk' ,

          done : true 
        },
        {
          title : 'study',
          details : 'lorem lorem ,aknfkankanklnanklanflk' ,

          done : false 
        },
        {
          title : 'sleep',
          details : 'lorem lorem ,aknfkankanklnanklanflk' ,

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
    },
    todoDone(payload){
      
      this.todos.map( (todo) => {
        if (todo == payload) {
          todo.done = !todo.done
        }
      })
      
    },
    delTodo(payload){
      
      this.todos = this.todos.filter(todo => todo != payload)
      
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

    .btn {
        padding: 0.5rem 1rem;
        border: none;
        outline: none;
        border-radius: 5px;
        box-shadow: 0 0 3px rgb(223, 223, 223);
    }
    .btn-sucess {
        background: rgb(45, 177, 40);
        color:rgb(216, 231, 218) ;
    }
        .btn-primary {
        background: rgb(7, 75, 202);
        color:rgb(216, 231, 218) ;
    }
    .btn:hover {
        transform: scale(1.03);
        cursor: pointer;
        color: white;

    }

        .btn-danger {
        background: rgb(192, 73, 73);
        color:rgb(216, 231, 218) ;
    }

</style>
