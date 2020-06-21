<template>
  <div>
    <div class="mt-3">
      <Intro :name="name" />
    </div>
    <Comments />
  </div>
</template>

<script>
import Intro from '@/components/Home/Intro'
import Comments from '@/components/Home/Comments'
export default {
  name: 'Home',
  components: {
    Intro,
    Comments
  },
  data: () => ({
    name: 'Максим'
  })
}
</script>

<style></style>
