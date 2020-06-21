<template>
  <nav class="col-md-2 d-none d-md-block bg-light sidebar">
    <div class="sidebar-sticky">
      <ul class="nav flex-column">
        <li v-for="link in links" :key="link.url" class="nav-item">
          <router-link
            class="nav-link"
            :class="{ active: link.url == $route.path }"
            :to="link.url"
          >
            <span data-feather="home"></span>
            {{ link.title }}
          </router-link>
        </li>
      </ul>
    </div>
  </nav>
</template>

<script>
export default {
  name: 'sidebar',
  data: () => ({
    links: [
      { title: 'Главная', url: '/' },
      { title: 'Список дел', url: '/todo' },
      { title: 'Галлерея', url: '/gallery' }
    ]
  })
}
</script>

<style lang="sass" scoped></style>
