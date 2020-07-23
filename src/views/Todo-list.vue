<template>
  <div class="todo-list">
    <h1>Todo List</h1>
    <TodoList />
  </div>
</template>

<script>
import TodoList from '@/components/TodoList.vue'

export default {
  name: 'Todo-list',
  components : {
    TodoList
  }
}
</script>

<style lang="sass" scoped>



  
</style>