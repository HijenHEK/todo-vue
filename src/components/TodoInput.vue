<template>
    <div id="TodoInput">
            <input type="text" v-model="newTodo" @keydown="typingTodo">
            <button @click="addTodo">add</button>
            <div class="err" v-if="err">{{err}}</div>
       
    </div>
</template>



<script>
export default {
    data () {
        return {
            newTodo : '',
            err : ''
        }
    },
    methods : {
        addTodo() {
            if(this.newTodo) {
                this.$emit('addTodo' , this.newTodo)
                
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