<template>
  <div>
    <h3>Последние публикации за сутки:</h3>
    <hr />
    <CommentItem
      v-for="comment in comments"
      :key="comment.id"
      :comment="comment"
    />
  </div>
</template>

<script>
import CommentItem from '@/components/Home/CommentItem'
export default {
  name: 'comments',
  components: {
    CommentItem
  },
  data: () => ({
    comments: []
  }),
  mounted() {
    fetch('https://jsonplaceholder.typicode.com/comments?_limit=5')
      .then(response => response.json())
      .then(json => {
        this.comments = json
      })
  }
}
</script>

<style lang="sass" scoped></style>
