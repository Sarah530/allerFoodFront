<template>
  <div id="app">


    <v-app id="inspire">

      <v-app-bar
          prominent
          app
          color="white"
      >

        <v-app-bar-nav-icon
            @click.stop="drawer = !drawer"
            x-large
            color="#85CB85"
        >
        </v-app-bar-nav-icon>


        <v-container fluid>
          <v-layout fill-height justify-center>

            <v-img
                src="../assets/logo1_transparent.png"
                max-height="120"
                max-width="120"


            ></v-img>

          </v-layout>
        </v-container>
        <v-spacer></v-spacer>

        <v-btn icon>
          <v-icon @click.stop="drawer_accountIcon = !drawer_accountIcon" x-large color="#CBB885">mdi-account-circle
          </v-icon>
        </v-btn>

      </v-app-bar>

      <!-- menu hamburger dropdown-->
      <v-navigation-drawer
          v-model="drawer"
          absolute
          temporary

      >
        <v-list
            nav
        >
          <v-list-item
              v-for="item in menuItems"
              :key="item.title"
              :to="item.path">
            <v-list-tile-action>
              <v-icon>{{ item.icon }}</v-icon>
            </v-list-tile-action>
            <v-list-tile-content>{{ item.title }}</v-list-tile-content>
          </v-list-item>

        </v-list>
      </v-navigation-drawer>


      <!-- icone du profil dropdown-->
      <v-navigation-drawer
          v-model="drawer_accountIcon"
          absolute
          temporary

      >
        <v-list
            nav
        >

          <v-list-item
              v-for="item in profilMenuItems"
              :key="item.title"
              :to="item.path">
            <v-list-tile-action>
              <v-icon>{{ item.icon }}</v-icon>
            </v-list-tile-action>
            <v-list-tile-content>{{ item.title }}</v-list-tile-content>
          </v-list-item>


        </v-list>
      </v-navigation-drawer>

    </v-app>

  </div>

</template>


<script>
export default {
  name: "NavBar.vue",

  data: () => ({
    drawer: false,
    group: null,
    drawer_accountIcon: false,
    group2: null,
    menuItems: [
      {title: 'Accueil', path: '/', icon: 'home'},
      {title: 'Inscription', path: '/inscription', icon: 'face'},
      {title: 'Connexion', path: '/connexion', icon: 'lock_open'},
      {title: 'Recettes', path: '/recettes', icon: 'book'}
    ],
    profilMenuItems: [
      {title: 'Inscription', path: '/inscription', icon: 'face'},
      {title: 'Connexion', path: '/connexion', icon: 'lock_open'},
    ]

  }),


}


</script>

<style scoped>

</style>