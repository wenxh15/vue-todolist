<template>
  <div>
    <div :key="todo.id" v-for="todo in todos">
      <TodoItem :todo="todo" @deleteTodo='deleteTodo'/>
    </div>
  </div>
</template>

<script>
import TodoItem from "./TodoItem";

export default {
  name: "Todos",
  components: {
    TodoItem
  },
  props: {
    todos: {
      type: Array
    }
  },
  methods:{
    deleteTodo(id){
      console.log(id)
      this.$emit('deleteTodo',id)
    }
  }
};
</script>


<style scoped>
</style>


