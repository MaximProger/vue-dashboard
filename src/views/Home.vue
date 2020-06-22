<template>
  <div>
    <div class="mt-3">
      <Intro :name="name" />
    </div>
    <Comments />
    <Form />
  </div>
</template>

<script>
import Intro from '@/components/Home/Intro'
import Comments from '@/components/Home/Comments'
import Form from '@/components/Home/Form'
export default {
  name: 'Home',
  components: {
    Intro,
    Comments,
    Form
  },
  data: () => ({
    name: 'Максим'
  })
}
</script>

<style></style>
