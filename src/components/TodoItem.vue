<template lang="pug">
    label(:for="`todo-${todo.id}`" class="container")
        div(class="container-checkbox")
            input(:id="`todo-${todo.id}`" :checked="todo.done" @change="setDone" type="checkbox" class="checkbox")
        div(class="container-title")
            h2(class="title" v-bind:class="{'todo-done':todo.done}") {{todo.title}}
</template>
<script>
export default {
    name: 'TodoItem',
    props: ['todo'],
    methods: {
        setDone(){
            this.todo.done = !this.todo.done;
        }
    }
}
</script>
<style lang="scss" scoped>
    .container{
        display: block;
        width: 100%;
        margin-bottom: 10px;
        .container-checkbox{
            display: inline;
            .checkbox{
                transform: translate(50%, -50%);
            }
        }
        .container-title{
            display: inline;
            .title{
                display: inline;
                margin-left: 15px;
            }
        }
    }
    .todo-done{
        transition: ease-in .2s;
        text-decoration: line-through;
        opacity: 0.4;
    }
</style>
