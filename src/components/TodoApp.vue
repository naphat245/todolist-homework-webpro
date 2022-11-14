<template>
  <div>
      <h6>To Do List</h6>
      <TodoForm />
      <TodoList />
  </div>
</template>

<script>
import TodoForm from "../components/TodoForm.vue"
import TodoList from "../components/TodoList.vue"
export default {
    name:"TodoApp",
    components: { TodoForm, TodoList }
}
</script>

<style>

</style>