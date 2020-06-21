<template>
  <nav class="col-md-2 d-none d-md-block bg-light sidebar">
    <div class="sidebar-sticky">
      <ul class="nav flex-column">
        <li class="nav-item">
          <router-link class="nav-link active" to="/">
            <span data-feather="home"></span>
            Главная <span class="sr-only">(current)</span>
          </router-link>
        </li>
        <li class="nav-item">
          <router-link class="nav-link" to="/todo">
            <span data-feather="file"></span>
            Список дел
          </router-link>
        </li>
        <li class="nav-item">
          <router-link class="nav-link" to="/gallery">
            <span data-feather="shopping-cart"></span>
            Галлерея
          </router-link>
        </li>
      </ul>
    </div>
  </nav>
</template>

<script>
export default {
  name: 'sidebar'
}
</script>

<style lang="sass" scoped></style>
