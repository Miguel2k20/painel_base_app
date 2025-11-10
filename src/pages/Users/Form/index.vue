<template>
  <div class="row">
    <div class="col-md-12">
      <FormUser :model="model"></FormUser>
    </div>
  </div>
</template>

<script>
import FormUser from "./components/FormUser.vue";
import axios from "axios";

export default {
  components: { FormUser },
  data() {
    return {
      model: {}, // modelo inicial vazio
    };
  },
  async created() {
    const id = this.$route.params.id;
    if (id) {
      try {
        const response = await axios.get(`http://localhost:3000/users/${id}`);
        console.log(response.data);
        // this.model = response.data;
      } catch (error) {
        console.error("Erro ao buscar usuário:", error);
      }
    }
  },
};
</script>
