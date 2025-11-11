<template>
  <div class="d-flex justify-content-center align-items-center vh-100 p-1">
    <card
      type="login"
      class="w-100 mt-5"
      style="max-width: 500px; padding: 2rem;"
    >
      <div class="img d-flex justify-content-center">
        <img
          src="/img/icons/jupterLogo.png"
          alt="..."
          class="img-fluid"
          style="max-width: 100px;"
        />
      </div>
      <h1 class="title text-center mt-3">Jupiter Dashboard!</h1>

      <form class="login-form mt-4">
        <base-input
          label="E-mail"
          placeholder="E-mail"
          v-model="model.email"
        />
        <base-input
          label="Senha"
          placeholder="Senha"
          v-model="model.password"
        />
        <div class="text-center mt-4">
          <base-button type="primary" @click="submitForm(model)" fill>Entrar</base-button>
        </div>
      </form>
    </card>
  </div>
</template>

<script>
import { login } from '@/services/routesApi/login';

export default {
  name: "LoginCard",
  data() {
    return {
      model: {
        email: "",
        password: ""
      }
    }
  },
  methods: {
    submitForm(formData) {
      login(formData)
        .then(response => {
          localStorage.setItem('user', JSON.stringify(response.data));
          this.$router.push('/dashboard');
        })
        .catch(error => {
          console.error('Login failed:', error);
        });
    }
  }
}
</script>
