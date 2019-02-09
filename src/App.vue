<template lang="pug">
  div(id="app")
    Header
    AddTodo(@addTodo="addTodo")
    
    div(id="container-todolist")
      TodoList(v-bind:todos="todos" @todoDelete="todoDelete")

    p Made with love <3
    p 2019
</template>

<script>
import Header from './components/layout/Header'
import AddTodo from './components/AddTodo'
import TodoList from './components/TodoList'

export default {
  name: 'app',
  components: {
    Header,
    AddTodo,
    TodoList
  },
  data() {
    return {
      todos: [
        {
          id: 1,
          title: 'Take out the trash.',
          done: false
        },
        {
          id: 2,
          title: 'Call Mike.',
          done: true
        },
        {
          id: 3,
          title: 'Feed the cat.',
          done: false
        },
      ],
    }
  },
  methods: {
    todoDelete(id){
      this.todos = this.todos.filter(todo => todo.id !== id)
    },
    addTodo(new_todo){
      this.todos = [
        new_todo,
        ...this.todos
      ]
    }
  },
}
</script>

<style lang="scss">
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
  outline: none;
}
body{
  background-color: #fcfbff;
}
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  margin: 10px;
  #container-todolist {
    padding: 10px 5px 0px;
    margin-bottom: 25px;
    border: 1px solid #ccc;
    border-bottom-right-radius: 5px;
    border-bottom-left-radius: 5px;
    background-color: #fff;
  }
  p {
    text-align: center;
    color: #aaa;
    font-size: .8em;
  }
}
.clear{
  clear: left;
}
</style>
