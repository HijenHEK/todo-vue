<template>
    <div id="todo">
        <div class="title"  :class="{'done' : todo.done}">
            {{todo.title}}
        </div>
        <div class="controls">
            <button class="btn btn-sucess" v-if="!todo.done" @click="todoDone(todo)">done ?</button>
            <button class="btn btn-primary" v-if="todo.done" @click="todoDone(todo)">not done ?</button>
             <button class="btn btn-danger" @click="delTodo(todo)"> delete </button>
        </div>
    </div>
</template>


<script>
export default {
    props : ['todo'],
    methods : {
        todoDone(todo){
            this.$emit('todoDone' , todo) ;
        },
        delTodo(todo){
            this.$emit('delTodo' , todo) ;
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
        height: 2rem;
        display: flex;
        align-items: center;
        justify-content: space-between;
        background-color: rgb(238, 238, 238);
        border-radius: 5px;
        box-shadow: 0 0 3px rgb(223, 223, 223);
        font-size: 1.3rem;
        

    }

    .controls > .btn:last-child {
        margin-left: 0.5rem ;
    }

</style>