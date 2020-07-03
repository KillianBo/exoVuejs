<template>
    <div class="connexion">
        <h1>Connexion</h1>
        <v-form>
        <v-text-field type="text" label="Identifiant" v-model="login"></v-text-field>
        <v-text-field type="password" label="Mot de passe" v-model="password"></v-text-field>
        <v-btn @click="connexionAction" color="primary">Connexion</v-btn>
        <v-alert v-if="error" type="error">{{ error }}</v-alert>
        </v-form>
    </div>
</template>

<script>
    export default {
        data() {
            return {
            login: "",
            password: "",
            error: ""
            };
        },
        methods: {
            async connexionAction() {
            const testConnexion = await this.axios.get(`http://localhost:3000/users`,{
                    params: {
                        login: this.login,
                        password: this.password
                    }
                }
            );

            if (testConnexion.data.length) {
                this.error = "ok";
            } else {
                this.error = "Identifiant ou Mot de passe erroné!";
            }
            }
        }
    };
</script>

<style lang="scss" scoped>

</style>