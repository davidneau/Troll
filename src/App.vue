<template>
  <div>
    <nav v-if="connected">
      <router-link to="/">Accueil</router-link>
    </nav>

    <router-view></router-view>
  </div>
</template>

<script>


export default {
  name: 'App',
  data() {
    return {
        connected: false
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

body {
  background-image: url("../Assets/Img/fondecran.jpg");
  background-size: cover;      /* l’image couvre tout l’écran */
  background-position: center; /* centrée */
  background-repeat: no-repeat;/* pas de répétition */
  background-attachment: fixed;/* reste fixe au scroll (optionnel) */
}
</style>
