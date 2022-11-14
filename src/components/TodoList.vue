<template>
  <div class="q-pt-md" v-if="store.todoList.length > 0">
    <q-list bordered separator>
      <q-item clickable v-ripple v-for="todo in store.todoList" :key="todo.id">
        <q-item-section :class="{ completeClass: todo.completed }">
          {{ todo.item }}</q-item-section
        >
        <q-item-section avatar>
          <q-icon
            name="check"
            color="primary"
            @click.stop="store.toggleCompleted(todo.id)"
          />
        </q-item-section>
        <q-item-section avatar>
          <q-icon
            name="delete"
            color="primary"
            @click="store.deleteToDo(todo.id)"
          />
        </q-item-section>
      </q-item>
    </q-list>
  </div>
  <div class="q-pt-md" v-else>No Data</div>
</template>

<script>
import { useTodoStore } from "../stores/todoList";
export default {
  name: "TodoList",
  data() {
    return { store: useTodoStore() };
  },
};
</script>

<style>
.completeClass {
  text-decoration: line-through;
}
</style>
