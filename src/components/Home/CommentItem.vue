<template>
  <div class="card mb-2">
    <div class="card-header">
      {{ comment.email }}
    </div>
    <div class="card-body">
      <h5 class="card-title">{{ comment.name }}</h5>
      <p class="card-text">
        {{ comment.body }}
      </p>
      <!-- <a href="#" class="btn btn-primary">Переход куда-нибудь</a> -->
    </div>
  </div>
</template>

<script>
export default {
  name: 'commentsitem',
  props: ['comment']
}
</script>

<style lang="scss" scoped>
.card-title {
  &::first-letter {
    text-transform: capitalize;
  }
}

.card-text {
  &::first-letter {
    text-transform: capitalize;
  }
}
</style>
