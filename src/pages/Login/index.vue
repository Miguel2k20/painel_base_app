<template>
  <card type="login">
    <div class="img d-flex justify-content-center">
      <img src="/img/icons/jupterLogo.png" alt="..." style="width: 100%; max-width: 100px;" />
    </div>
    <h1 class="title text-center mt-3">Jupiter Dashboard!</h1>

    <form class="login-form">
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
        <base-button slot="footer" type="primary" fill>Entrar</base-button>
    </form>
  </card>
</template>

<script>
export default {
  name: "LoginCard",
  data() {
    return {
      model: {
        email: "",
        password: ""
      }
    }
  }
}
</script>
