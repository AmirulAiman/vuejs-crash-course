<template>
    <div>
        <form @submit="addTodo">
            <input type="text" v-model="task" name="task" placeholder="Task...">
            <input type="submit" value="submit" class="btn">
        </form>
    </div>
</template>

<script>
export default {
    name:'AddTodo',
    data(){
        return{
            task:'',
        }
    },
    methods:{
        addTodo(e){
            e.preventDefault();
            const newTodo = {
                title:this.task,
                completed:false
            }
            //Send to parent(App.vue)
            this.$emit('add-todo',newTodo);
            this.title = '';
        }
    }
}
</script>

<style scoped>
    form{
        display: flex;
    }
    input[type="text"]{
        flex:10;
        padding:5px;
    }
    input[type="submit"]{
        flex:2;
    }
</style>
