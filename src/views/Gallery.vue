<template>
  <div class="mt-3 mb-3">
    <h3>Gallery</h3>
    <hr />
    <GalleryList :photos="photos" />
  </div>
</template>

<script>
import GalleryList from '@/components/Gallery/GalleryList'
export default {
  name: 'gallery',
  components: {
    GalleryList
  },
  data: () => ({
    photos: []
  }),
  mounted() {
    fetch('https://jsonplaceholder.typicode.com/photos?_limit=50')
      .then(response => response.json())
      .then(json => {
        this.photos = json
      })
  }
}
</script>

<style lang="sass" scoped></style>
