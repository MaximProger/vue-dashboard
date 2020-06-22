<template>
  <div class="mt-5 mb-5">
    <h3 class="text-center">Понравился дашборд? Оставьте отзыв!</h3>
    <p class="small text-center">Ваше мнение очень важно для нас</p>
    <hr />
    <form @submit.prevent="submitHandler">
      <div class="form-group">
        <label for="name">Ваше имя</label>
        <input
          type="text"
          class="form-control"
          id="name"
          aria-describedby="emailHelp"
          v-model.trim="name"
          :class="{
            'is-invalid': $v.name.$dirty && !$v.name.required
          }"
        />
        <small
          v-if="$v.name.$dirty && !$v.name.required"
          id="emailHelp"
          class="form-text text-muted"
          >Вы не ввели имя</small
        >
      </div>
      <div class="form-group">
        <label for="exampleInputEmail1">Электронная почта</label>
        <input
          type="email"
          class="form-control"
          id="exampleInputEmail1"
          aria-describedby="emailHelp"
          v-model.trim="email"
          :class="{
            'is-invalid':
              ($v.email.$dirty && !$v.email.required) ||
              ($v.email.$dirty && !$v.email.email)
          }"
        />
        <small
          v-if="$v.email.$dirty && !$v.email.required"
          id="emailHelp"
          class="form-text text-muted"
          >Поле email не должно быть пустым</small
        >
        <small
          v-if="$v.email.$dirty && !$v.email.email"
          id="emailHelp"
          class="form-text text-muted"
          >Введите корректный email</small
        >
      </div>
      <div class="form-group">
        <label for="exampleFormControlTextarea1">Сообщение</label>
        <textarea
          class="form-control"
          id="exampleFormControlTextarea1"
          rows="3"
          v-model.trim="message"
          :class="{
            'is-invalid': $v.message.$dirty && !$v.message.required
          }"
        ></textarea>
        <small
          v-if="$v.message.$dirty && !$v.message.required"
          id="emailHelp"
          class="form-text text-muted"
          >Введите сообщение</small
        >
      </div>
      <div class="form-group form-check">
        <input
          v-model="agree"
          type="checkbox"
          class="form-check-input"
          id="exampleCheck1"
        />
        <label class="form-check-label" for="exampleCheck1"
          >Я безоговорочно принимаю политику конфиденциальности</label
        >
      </div>
      <button type="submit" class="btn btn-dark">Отправить</button>
    </form>
  </div>
</template>

<script>
import { email, required } from 'vuelidate/lib/validators'
export default {
  data: () => ({
    name: '',
    email: '',
    message: '',
    agree: false
  }),
  validations: {
    name: { required },
    email: { email, required },
    message: { required },
    agree: { checked: v => v }
  },
  methods: {
    async submitHandler() {
      if (this.$v.$invalid) {
        this.$v.$touch()
        return
      }
    }
  }
}
</script>

<style lang="scss" scoped></style>
