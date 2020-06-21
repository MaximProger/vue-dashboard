<template>
  <nav class="navbar navbar-dark fixed-top bg-dark flex-md-nowrap p-0 shadow">
    <router-link class="navbar-brand col-sm-3 col-md-2 mr-0" to="/"
      >Фобос Групп</router-link
    >
    <input
      class="form-control form-control-dark w-100"
      type="text"
      placeholder="Искать"
      aria-label="Search"
    />
    <ul class="navbar-nav px-3">
      <li class="nav-item text-nowrap">
        <a class="nav-link" href="#">Выйти</a>
      </li>
    </ul>
  </nav>
</template>

<script>
export default {
  name: 'navbar'
}
</script>

<style lang="sass" scoped></style>
