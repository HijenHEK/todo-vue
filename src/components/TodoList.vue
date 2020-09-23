<template>
    <div id="todoList">
        <TodoItem v-for="(todo, index) in todos" :key="index" :todo="todo" @del-todo="$emit('del-todo' , todo)" @todo-done="$emit('todo-done' , todo)"/>
    </div>
</template>

<script>
import TodoItem from './TodoItem'
export default {
    props : ['todos'],
    components :{
        TodoItem
    },
    data() {
        return {
            
        }
    },

}
</script>

<style scoped>

</style>