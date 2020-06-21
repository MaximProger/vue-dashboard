<template>
  <tr>
    <th scope="row">{{ index + 1 }}</th>
    <td class="title">{{ todo.title }}</td>
    <td>
      <span
        class="status"
        :class="{
          green: todo.completed === true,
          red: todo.completed === false
        }"
      >
        {{ todo.completed === true ? 'Выполненно' : 'Не выполненно' }}
      </span>
    </td>
    <td>
      <button
        type="button"
        class="btn btn-outline-danger"
        @click="$emit('remove-todo', todo.id)"
      >
        &times;
      </button>
    </td>
  </tr>
</template>

<script>
export default {
  name: 'todoitem',
  props: {
    todo: {
      type: Object
    },
    index: Number
  }
}
</script>

<style lang="scss" scoped>
.btn {
  border-radius: 50%;
}

.title {
  &:first-letter {
    text-transform: capitalize;
  }
}

.status {
  display: inline-block;
  padding: 5px;
  color: #fff;
  border-radius: 5px;
  min-width: 120px;
  width: 120px;
  text-align: center;

  &.red {
    background-color: rgb(184, 54, 54);
  }

  &.green {
    background-color: rgb(59, 161, 59);
  }
}
</style>
