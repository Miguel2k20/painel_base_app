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
                    <tr>
                        <th scope="row">1</th>
                        <td>João Miguel Mendonça</td>
                        <td>teste@teste.com</td>
                        <td class="d-flex">
                            <button class="btn btn-primary mr-3"><i class="tim-icons icon-pencil"></i></button>
                            <button class="btn btn-danger"><i class="tim-icons icon-trash-simple"></i></button>
                        </td>
                    </tr>
                    <tr>
                        <th scope="row">2</th>
                        <td>Clara Haag</td>
                        <td>teste@teste222222.com</td>
                        <td class="d-flex">
                            <a href="/users/edit/1" class="btn btn-primary mr-3"><i class="tim-icons icon-pencil"></i></a>
                            <button class="btn btn-danger"><i class="tim-icons icon-trash-simple"></i></button>
                        </td>
                    </tr>
                    
                </tbody>
            </table>
        </div>
    </div>
</template>