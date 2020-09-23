<template>
    <div id="todo">
        <div class="title"  :class="{'done' : todo.done}">
            {{todo.title}}
        </div>
        <div class="controls">
            <button class="btn btn-sucess" v-if="!todo.done">done ?</button>
             <button class="btn btn-danger"> delete </button>
        </div>
    </div>
</template>


<script>
export default {
    props : ['todo']
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
    .btn {
        padding: 0.5rem 1rem;
        border: none;
        border-radius: 5px;
        box-shadow: 0 0 3px rgb(223, 223, 223);
    }
    .btn-sucess {
        background: rgb(45, 177, 40);
        color:rgb(216, 231, 218) ;
    }
    .btn-sucess:hover {
        background: rgb(45, 177, 40);
        color: white;
    }
        .btn-danger {
        background: rgb(192, 73, 73);
        color:rgb(216, 231, 218) ;
    }
    .btn-danger:hover {
        background: rgb(192, 73, 73);
        color: white;
    }
</style>