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
import { getUser } from "@/services/routesApi/users";

export default {
  components: { FormUser },
  data() {
    return {
      model: {}, 
    };
  },
  async created() {
    const id = this.$route.params.id ?? null;
    if(id) this.fetchUser(id);
  },
  methods: {
    fetchUser(id){
      getUser(id).then(response => {
        console.log(response.data);
      }).catch(error => {
        console.error("Erro ao buscar usuário:", error);
      });
    }
  },
};
</script>
