<template>
    <div id="TodoInput">
            <div class="form">
                <input type="text" v-model="newTodo" @keydown="typingTodo">
                <button @click="addTodo">add</button>
            </div>
            <div class="err" v-if="err">{{err}}</div>
       
    </div>
</template>



<script>
export default {
    data () {
        return {
            newTodo :'',
            err : ''
        }
    },
    methods : {
        addTodo() {
            if(this.newTodo) {
                this.$emit('addTodo' , this.newTodo)
                this.newTodo = ''
                
            }else {
                this.err = 'emty field !'
            }
        },
        typingTodo(){
            this.err = ''

        }
    },
    
}
</script>


<style scoped>
    #TodoInput {
        width: 100%;
        display: flex;
        flex-direction: column;
        align-items: stretch;
        justify-content: center;
        position: relative;
        margin: 2rem 0 ;

    }

    .form {
        flex: 1;
        width: 100%;
        max-width: 350px;

        margin: 0 auto;
        display: flex;
        justify-content: space-between;
        
    }
    .err {
        padding: 0.5rem 1rem;
        width: 100px;
        background-color: rgba(192, 137, 137, 0.8);
        color: white;
        border-radius: 5px;
        position: absolute;
        right: -80px;     
        height: 1.5rem;
        
 

    }
    .form input {
        flex: 0.8;
        padding: 0.5rem 1rem;
        outline: none;
        border: none;
        background-color: rgb(238, 238, 238);
        border-radius: 5px;
        box-shadow: 0 0 3px rgb(223, 223, 223);
                height: 1.5rem;

        
    }
    .form button {
        flex: 0.15;
        padding: 0.5rem;
        border-radius: 5px;
        border: none;
        box-shadow: 0 0 3px rgb(223, 223, 223);


    }
</style>