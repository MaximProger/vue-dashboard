<template>
  <div class="mt-3">
    <h2>Список дел</h2>
    <hr />
    <TodoList :todos="todos" @remove-todo="removeTodo" />
  </div>
</template>

<script>
import TodoList from '@/components/Todo/TodoList'
export default {
  name: 'todo',
  components: {
    TodoList
  },
  data: () => ({
    todos: []
  }),
  mounted() {
    fetch('https://jsonplaceholder.typicode.com/todos?_limit=20')
      .then(response => response.json())
      .then(json => {
        this.todos = json
      })
  },
  methods: {
    removeTodo(id) {
      this.todos = this.todos.filter(t => t.id !== id)
    }
  }
}
</script>

<style lang="sass" scoped></style>
