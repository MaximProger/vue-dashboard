<template>
  <div class="card col-4 mt-2 mb-2">
    <img :src="photo.url" class="card-img-top" :alt="photo.title" />
    <div class="card-body">
      <p class="card-text">
        {{ photo.title }}
      </p>
    </div>
  </div>
</template>

<script>
export default {
  name: 'galleryitem',
  props: ['photo']
}
</script>

<style lang="scss" scoped>
.card-text {
  &::first-letter {
    text-transform: capitalize;
  }
}
</style>
