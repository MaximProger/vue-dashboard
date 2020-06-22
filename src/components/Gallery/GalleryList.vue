<template>
  <div class="row">
    <GalleryItem v-for="photo in photos" :key="photo.id" :photo="photo" />
  </div>
</template>

<script>
import GalleryItem from '@/components/Gallery/GalleryItem'
export default {
  name: 'gallerylist',
  components: {
    GalleryItem
  },
  props: ['photos']
}
</script>

<style lang="scss" scoped></style>
