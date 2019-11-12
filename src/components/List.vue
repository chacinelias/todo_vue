<template>
    <div id="root" class="container" style="border: solid 2px">
        <div class="display-2" style="text-align: center">To Do List</div>

        <div v-for="(todo, index) in todos" :key="index">
            <div class="row">

                <div class="col-11">
                    <Todo/>
                </div>
            </div>
        </div>
        <AddTodo @addTodo="addTodo"/>
    </div>
</template>

<script>
import Todo from './Todo.vue'
import AddTodo from './AddTodo.vue';

export default {
    name: 'List',
    data() {
        return {
            todos: []
        }
    },
    methods: {
        addTodo() {
            this.todos.push(Todo);
        }
    },
    components: {
        Todo,
        AddTodo
    }
}
</script>

<style scoped>

</style>