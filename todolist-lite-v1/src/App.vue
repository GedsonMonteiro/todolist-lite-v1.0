<template>
  <h1>Lista de Tarefas</h1>
  <TodoList/>  
</template>

<script>
import TodoList from './components/TodoList.vue'

export default {
  name: 'App',
  components: {
    TodoList
  }
}
</script>

<style>

</style>