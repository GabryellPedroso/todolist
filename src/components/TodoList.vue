<template lang="pug">
    div
        div(v-for="todo in todos")
            TodoItem(v-bind:todo="todo")
</template>
<script>
import TodoItem from './TodoItem.vue'

export default {
    name: 'TodoList',
    components: {
        TodoItem,
    },
    props: ['todos']
}
</script>
<style lang="scss" scoped>
    h1{
        color: 'red';
    }
</style>
