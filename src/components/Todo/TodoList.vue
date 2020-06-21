<template>
  <table class="table">
    <thead class="thead-dark">
      <tr>
        <th scope="col">#</th>
        <th scope="col">Наименование</th>
        <th scope="col">Статус</th>
        <th scope="col">Удалить</th>
      </tr>
    </thead>
    <tbody>
      <TodoItem
        v-for="(todo, i) in todos"
        :todo="todo"
        :key="todo.id"
        :index="i"
        @remove-todo="removeTodo"
      />
    </tbody>
  </table>
</template>

<script>
import TodoItem from '@/components/Todo/TodoItem'
export default {
  name: 'todolist',
  components: {
    TodoItem
  },
  props: ['todos'],
  methods: {
    removeTodo(id) {
      this.$emit('remove-todo', id)
    }
  }
}
</script>

<style lang="sass" scoped></style>
