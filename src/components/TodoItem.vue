<template>
  <div class='todo-item' :class='{"is-complete":todo.completed}'>
    <p>
    <input type='checkbox' @change='markComplete'/>{{todo.title}}
    <button @click='deleteTodo'>x</button>
    </p>
  </div>
</template>


<script>
export default {
  name: "TodoItem",
  props:{
    todo: {
      type: Object
    }
  },
  methods:{
    markComplete() {
      this.todo.completed = !this.todo.completed;
    },
    deleteTodo() {
      this.$emit('deleteTodo',this.todo.id)
    }
  }
};
</script>


<style scoped>
.todo-item {
  background:lightgray;
  padding:10px;
  border-bottom: 1px #ccc dotted

}
.is-complete{
  text-decoration:line-through;
}

</style>
