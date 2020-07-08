<template>
    <v-form @submit.prevent="onSubmit" ref="form">
        <input type="text" v-model="title">
        <v-btn small color="primary" type="submit">Create</v-btn>
    </v-form>
</template>

<script>
    export default {
        data () {
            return {
             title: ''
            }
        },
        methods: {
            onSubmit() {
                if (this.title.trim()){
                    const newTodo = {
                        id: Date.now(),
                        title: this.title,
                        completed: false
                    }
                    this.$emit('add-todo', newTodo)
                    this.title = ''
                }
            }
        }
    }
</script>

<style scoped>
    input {
        width: 500px;
        border-style: outset;
    }
</style>