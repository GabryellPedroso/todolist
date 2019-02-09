<template lang="pug">
  div(id="app")
    Header
    
    div(id="container-todolist")
      TodoList(v-bind:todos="todos" @todoDelete="todoDelete")
</template>

<script>
import Header from './components/layout/Header'
import TodoList from './components/TodoList'

export default {
  name: 'app',
  components: {
    TodoList,
    Header
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
    border: 1px solid #ccc;
    border-bottom-right-radius: 5px;
    border-bottom-left-radius: 5px;
    background-color: #fff;
  }
}
.clear{
  clear: left;
}
</style>
