<template>
    <div id="todoList">
        <TodoItem v-for="(todo, index) in todos" :key="index" :todo="todo" @delTodo="$emit('delTodo' , todo)" @todoDone="$emit('todoDone' , todo)"/>
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