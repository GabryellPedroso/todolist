<template lang="pug">
    div.container
        label(:for="`todo-${todo.id}`" class="todo")
            div(class="container-checkbox")
                input(:id="`todo-${todo.id}`" :checked="todo.done" @change="setDone" type="checkbox" class="checkbox")
            
            div(class="container-title")
                h2(class="title" v-bind:class="{'todo-done':todo.done}") {{todo.title}}
        
        button(@click="$emit('todoDelete', todo.id)" type="button" class="container-btnDelete")
                span X

</template>
<script>
export default {
    name: 'TodoItem',
    props: ['todo'],
    methods: {
        setDone(){
            this.todo.done = !this.todo.done;
        },
        todoDelete(){
            console.log('foi')
        }
    }
}
</script>
<style lang="scss" scoped>
    .container{
        position: relative;
    }
    .todo{
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
    .container-btnDelete{
        transition: ease-out .2s;
        position: absolute;
        right: 0px;
        top: 50%;
        transform: translate(-50%, -50%);
        display: inline;
        background-color: #fff;
        padding: 3px 6px;
        border: 1px solid #c23616;
        border-radius: 50%;
        color: #c23616;
        font-weight: bold;
        font-size: .8em;
        &:active{
            opacity: .5;
        }
    }
    .todo-done{
        transition: ease-in .2s;
        text-decoration: line-through;
        opacity: 0.4;
    }
</style>
