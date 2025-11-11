<template>
    <section id="section">
        <h1>{{ welcomeMessage }}</h1>
        <p>Estamos felizes em ter você conosco!</p>
    </section>
</template>
<script>
export default {
    name: "WelcomePage",
    data(){
        return {
            welcomeMessage: null
        }
    },
    created(){
        this.fetchUserName()
    },
    methods: {
        fetchUserName() {
            const user = JSON.parse(localStorage.getItem('user'));
            if (user && user.name) {
                this.userName = user.name;

                const hora = new Date().getHours();
                let saudacao = '';

                if (hora >= 5 && hora < 12) {
                saudacao = 'Bom dia';
                } else if (hora >= 12 && hora < 18) {
                saudacao = 'Boa tarde';
                } else if (hora >= 18 && hora < 24) {
                saudacao = 'Boa noite';
                } else {
                saudacao = 'Boa madrugada';
                }

                this.welcomeMessage = `${saudacao}, ${this.userName}!`;
            }
        }
    }
};
</script>