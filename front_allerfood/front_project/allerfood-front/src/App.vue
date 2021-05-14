<template>

  <div id="app">

    <v-app>

      <NavBar/>

      <v-content class="margeChelou">
        <router-view></router-view>
      </v-content>


      <!--
      <router-link to="/">Home</router-link> |
      <router-link to="/about">About</router-link>
       -->
    </v-app>


  </div>

</template>


<script>

import NavBar from "./components/NavBar";


export default {
  name: ' NavBar',
  components: {NavBar},


}

</script>


<style lang="scss">

.margeChelou {
  position: absolute;
  top: 20px;
  margin-left: 10px;
}

/*
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

#nav {
margin-top: 150px;
  padding: 30px;

  a {
    font-weight: bold;
    color: #2c3e50;

    &.router-link-exact-active {
      color: #42b983;
    }
  }
}
*/

</style>
