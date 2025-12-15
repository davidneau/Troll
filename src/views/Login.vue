<template>
  <div>
    <h1>Login</h1>
    <div>
        <div>
            email:
            <input id="login" type="text"/>
        </div>
        <div>
            mot de passe:
            <input id="pwd" type="password"/>
        </div>
        <div>Pas encore inscrit? cliquez <router-link to="/signup">ici</router-link></div>
        <button @click="validate">Valider</button>
    </div>
  </div>
</template>

<script>

export default {
  name: 'LoginView',
  methods: {
    validate(){
        let login = document.getElementById("login").value
        let pwd = document.getElementById("pwd").value
        console.log("login :", login, "pwd :", pwd)
        this.$router.push('/')
    }
  }
}
</script>

<style scoped>
</style>
