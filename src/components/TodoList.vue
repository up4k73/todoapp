<template>
    <div>
        <ul>
            <TodoItem
                    v-for="(todo, i) of todos"
                    v-bind:todo="todo"
                    v-on:remove-todo="removeTodo"
                    v-bind:index="i"
            />
        </ul>
    </div>
</template>

<script>
    import TodoItem from '@/components/TodoItem'
    export default {
        props: ['todos'],
        components: {
            TodoItem
        },
        methods: {
            removeTodo(id){
                console.log(id)
                this.$emit('remove-todo', id)
            },
            editTodo(id){
                this.$emit('editTodo', id)
            }
        }
    }
</script>

<style scoped>
    ul {
        list-style: none;
    }

</style>