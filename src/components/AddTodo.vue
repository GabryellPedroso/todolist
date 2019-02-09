<template lang="pug">
  div
    form(@submit="addTodo")
      input(type="text" v-model="title" placeholder="What will we do?")
      input(type="submit" value="Send")
</template>
<script>
import uuid from 'uuid'

export default {
  name: 'AddTodo',
  data(){
    return {
      title: ''
    }
  },
  methods: {
    addTodo(e){
      e.preventDefault();
            
      let title = this.title
      if (title) {
        title = this.titleFormat(title);

        const new_todo = {
          id: uuid.v4(),
          title,
          done: false
        }

        this.$emit('addTodo', new_todo)
        this.title = ''
      }
    },
    titleFormat(title){
      return title.charAt(0).toUpperCase() + title.slice(1);
    }
  }
}
</script>
<style lang="scss" scoped>
  form{
    display: flex;
  }
  input[type="text"]{
    flex: 10;
    padding: 5px;
    margin: 5px 0px;
    border: 1px solid #bbb;
  }
  input[type="submit"]{
    transition: ease-in .2s;
    display: inline-block;
    border: none;
    background: #333;
    color: #fff;
    flex: 2;
    padding: 5px;
    margin: 5px 0px 5px 4px;
    cursor: pointer;
    &:hover{
      background: #444e;
    }
  }
</style>
