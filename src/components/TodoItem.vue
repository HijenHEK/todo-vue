<template>
    <div id="todo" :class="{'done' : todo.done}">
        {{todo.title}}
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
</style>