<template>
    <div id="todo" >
        <div class="header" >
            <div class="title"  :class="{'done' : todo.done}" @click="hidden = !hidden">
            {{todo.title}}
            </div>
        <div class="controls">
            <button class="btn btn-sucess" v-if="!todo.done" @click="todoDone(todo)">done ?</button>
            <button class="btn btn-primary" v-if="todo.done" @click="todoDone(todo)">not done ?</button>
             <button class="btn btn-danger" @click="delTodo(todo)"> delete </button>
        </div>
        </div>


        <div class="body" @click="hidden = !hidden" :class="{'hidden' : hidden}">
            {{todo.details}}
        </div>
    </div>
</template>


<script>
export default {
    props : ['todo'],
    data() {
        return {
            hidden : true 
        }
    },
    methods : {
        todoDone(todo){
            this.$emit('todo-done' , todo) ;
        },
        delTodo(todo){
            this.$emit('del-todo' , todo) ;
        }
    }
}
</script>


<style scoped>
    .done {
        text-decoration: line-through ;
    }

    #todo {
        width: 80%;
        padding: 0.5rem 2rem;
        margin: 0.5rem auto;
        display: flex;
        flex-direction: column;
        background-color: rgb(238, 238, 238);
        border-radius: 5px;
        box-shadow: 0 0 3px rgb(223, 223, 223);
        font-size: 1.3rem;
        

    }
    .header {
        display: flex;
        align-items: center;
        justify-content: space-between;
        
    }
    
    .controls > .btn:last-child {
        margin-left: 0.5rem ;
    }
    .title {
        padding: 0.5rem 4rem 0.5rem 0 ;
        cursor: pointer;
    }
    .hidden {
        display: none;
    }
    .body {
        margin-top: 2rem;
    }
</style>