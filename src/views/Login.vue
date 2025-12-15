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
        fetch('https://pokemon-1xp8.onrender.com/message', {
            method: 'POST',
            headers: {
                'Content-Type': 'application/json'
            },
            body: JSON.stringify({
                message: {"login": login, "pwd": pwd}
            })
        })
        .then(res => res.json())
        .then(data => {
            console.log('Réponse serveur:', data)
        })
        .catch(err => console.error(err))
        this.$router.push('/home')
    }
  }
}
</script>

<style scoped>
</style>
