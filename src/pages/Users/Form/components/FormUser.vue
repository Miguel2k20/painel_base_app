<!-- eslint-disable vue/no-mutating-props -->
<template>
  <card>
    <h1 slot="header" class="title">
      {{ model.id ? 'Editar Colaborador' : 'Novo Colaborador' }}
    </h1>

    <div class="row">
      <div class="col-md-4 pr-md-1">
        <base-input
          label="Nome Do Colaborador"
          placeholder="Nome Do Colaborador"
          v-model="model.username"
        />
      </div>
      <div class="col-md-4 pl-md-1">
        <base-input
          label="Email Do Colaborador"
          placeholder="Email Do Colaborador"
          v-model="model.username"
        />
      </div>
      <div class="col-md-4 pl-md-1">
        <base-input
          label="Senha"
          placeholder="Senha"
          v-model="model.username"
        />
      </div>
    </div>
    <base-button slot="footer" type="primary" fill>Salvar</base-button>
  </card>
</template>
<script>
export default {
  props: {
    model: {
      type: Object,
      default: () => {
        return {};
      },
    },
  },
};
</script>
<style></style>
