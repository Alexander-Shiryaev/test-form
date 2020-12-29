<template>
  <div class="container mt-5">
    <div class="row">
      <div class="col-md-5 mx-auto">
        <form @submit.prevent="regUser" action ="localhost:8080" method ="POST">
          <div v-show="step === 1" class="next">
            <div class="form-group">
              <label for="name">Введите Ваше имя</label>
              <input v-model="formReg.name" type="text" class="form-control" id="name" required />
            </div>
            <div class="form-group">
              <label for="lastname">Введите Вашу фамилию</label>
              <input v-model="formReg.lastname" type="text" class="form-control" id="lastname" />
            </div>
            <div class="form-group">
              <label for="email">Введите Ваш email</label>
              <input v-model="formReg.email" type="email" class="form-control" id="email" required />
            </div>
            <button @click="nextStep" type="button" class="btn btn-info">
              Далее
            </button>
          </div>

          <div v-show="step === 2" class="next">
            <div class="form-group">
              <label for="login">Введите Ваш логин</label>
              <input v-model="formReg.login" type="text" class="form-control" id="login" required/>
            </div>
            <div class="form-group">
              <label for="password">Введите Ваш пароль</label>
              <input v-model="formReg.password" type="password" class="form-control" id="password" required/>
            </div>
            <div class="form-group">
              <label for="passwordConfirm">Подтвертите Ваш пароль</label>
              <input v-model="formReg.passwordConfirm" type="password" class="form-control" id="passwordConfirm" required/>
            </div>
            <div class="d-flex justify-content-between">
              <button @click="backStep" type="button" class="btn btn-info">Назад</button>
              <button type="submit" class="btn btn-danger">Регистрация</button>
            </div>
          </div>
        </form>
      </div>
    </div>
  </div>
</template>

<script>
import "bootstrap/dist/css/bootstrap.css";
import "bootstrap-vue/dist/bootstrap-vue.css";

export default {
  data() {
    return {
      step: 1,
      formReg: {
        name: '',
        lastname: '',
        email: '',
        login: '',
        password: '',
        passwordConfirm: '',
      }
    };
  },
  methods: {
    nextStep() {
      this.step++;
    },
    backStep() {
      this.step--;
    },
    regUser() {
      console.log('Вы зарегистрировались!')
      console.log(this.formReg.name)
      console.log(this.formReg.lastname)
      console.log(this.formReg.email)
      console.log(this.formReg.login)
      console.log(this.formReg.password)
    }
  },
};
</script>

<style>
#app {
}
</style>
