<template>
  <div id="app">
    <input placeholder='add something' v-model='value'/>
    <button @click='addTodo'>add</button>  
    <Todos :todos="todos" @deleteTodo='deleteTodo'/>
  </div>
</template>

<script>

import { v4 as uuidv4 } from 'uuid'
import Todos from "./components/Todos";

export default {
  name: "App",
  components: {
    Todos
  },
  data() {
    return {
      value:'',
      todos: [
        {
          id: 1,
          title: "Todo one",
          completed: false
        },
        {
          id: 2,
          title: "Todo two",
          completed: false
        },
        {
          id: 3,
          title: "Todo three",
          completed: false
        }
      ]
    };
  },
  methods:{
    addTodo() {
      let newTodo = {
        id: uuidv4(),
        title: this.value,
        completed: false
      };
      this.todos = [...this.todos, newTodo]
    },
    deleteTodo(id) {
      console.log(1);
      this.todos = this.todos.filter(todo => todo.id !== id)
    }
  }
};
</script>

<style>
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}
</style>
