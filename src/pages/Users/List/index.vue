<template>
    <div id="user-list">
        <div class="intro">
            <h1><b>Colaboradores</b></h1>
            <p>Lista de colaboradores cadastrados</p>
            <router-link to="/users/create" class="btn btn-secondary">
                Novo Colaborador
            </router-link>
        </div>
        <div class="content">
            <table class="table">
                <thead>
                    <tr>
                    <th scope="col">ID</th>
                    <th scope="col">Nome</th>
                    <th scope="col">Email</th>
                    <th scope="col">Ação</th>
                    </tr>
                </thead>
                <tbody>
                    <tr v-for="user in userList" :key="user.id">
                        <th scope="row">{{ user.id }}</th>
                        <td>{{ user.name }}</td>
                        <td>{{ user.email }}</td>
                        <td class="d-flex">
                            <a :href="`/users/edit/${user.id}`" class="btn btn-primary mr-3"><i class="tim-icons icon-pencil"></i></a>
                            <button @click="deleteUser(user.id)" class="btn btn-danger"><i class="tim-icons icon-trash-simple"></i></button>
                        </td>
                    </tr>
                    
                    
                </tbody>
            </table>
        </div>
    </div>
</template>

<script>
import { getUsers, deleteUser } from '@/services/routesApi/users';
export default {
  name: "UserList",
  data(){
    return {
        userList: []
    }
  },
  methods: {
    fetchUsers(){
        getUsers().then(response => {
            this.userList = response.data.users;
        }).catch(error => {
            console.error("Erro ao buscar usuários:", error);
        });
    },
    deleteUser(id){
        deleteUser(id).then(() => {
            this.userList = this.userList.filter(user => user.id !== id);
        }).catch(error => {
            console.error("Erro ao deletar usuário:", error);
        });
    }
  },
  created(){
    this.fetchUsers();
  }
};

</script>