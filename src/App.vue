<template lang="pug">
  div(id="app")
    div(id="container-logo")
      img(id="logo" alt="Vue logo" src="./assets/logo.png" width="40px")
      h1(id="title") Todo List
      div.clear
    
    div(id="container-todolist")
      TodoList(v-bind:todos="todos")
</template>

<script>
import TodoList from './components/TodoList'

export default {
  name: 'app',
  components: {
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
  }
}
</script>

<style lang="scss">
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
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
  #container-logo {
    padding: 10px 10px 5px;
    background-color: #222;
    border: 1px solid #111;
    border-top-right-radius: 5px;
    border-top-left-radius: 5px;
    #logo{
      float: left;
    }
    #title{
      display: block;
      color: #eee;
      float: left;
      margin-left: 15px;
    }
  }
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
