<template>
    <div id="app">
        <div v-for="todo in todos" :key="todo.id">
            <TodoItem :todo="todo" v-on:del-todo="$emit('del-todo',todo.id)"/>
        </div>
    </div>
</template>

<script>
import TodoItem from "./TodoItem";

export default {
    name:'todos',
    components:{
        TodoItem
    },
    props:["todos"],
    data(){
        return{
            msg:'Todos component'
        }
    }
}
</script>

<style scoped>

</style>


