<template>
  <div class="jumbotron">
    <h1 class="display-4">Привет, {{ name }}!</h1>
    <p class="lead">
      Вас приветсвует компания "Фобос Групп", добро пожаловать в наш дашборд.
    </p>
    <hr class="my-4" />
    <p>
      Недавно мы обновили галерею, вы можете увидить невероятные снимки перейдя
      по ссылке нижне:
    </p>
    <p class="lead">
      <router-link class="btn btn-primary btn-lg" to="/gallery" role="button"
        >Перейти в галерею</router-link
      >
    </p>
  </div>
</template>

<script>
export default {
  name: 'intro',
  props: ['name']
}
</script>

<style lang="sass" scoped></style>
