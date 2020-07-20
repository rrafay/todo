<template>
  <div class="grocery">
    <h1>Grocery List</h1>
    <TodoList />
  </div>
</template>

<script>
import TodoList from '@/components/TodoList.vue'

export default {
  name: 'Grocery',
  components : {
    TodoList
  }
}
</script>

<style lang="sass" scoped>



  
</style>