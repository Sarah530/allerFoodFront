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
        <!--menu hamburger si user connecté-->
        <v-list
            v-if="userConnected"
            nav
        >
          <v-list-item
              v-for="item in menuItemsIfConnected"
              :key="item.title"
              :to="item.path">
            <v-list-tile-action>
              <v-icon>{{ item.icon }}</v-icon>
            </v-list-tile-action>
            <v-list-tile-content>{{ item.title }}</v-list-tile-content>
          </v-list-item>
        </v-list>

        <!--menu hamburger si user non connecté-->
        <v-list
            v-else
            nav
        >
          <v-list-item
              v-for="item in menuItemsForAll"
              :key="item.title"
              :to="item.path">
            <v-list-tile-action>
              <v-icon>{{ item.icon }}</v-icon>
            </v-list-tile-action>
            <v-list-tile-content>{{ item.title }}</v-list-tile-content>
          </v-list-item>
        </v-list>
      </v-navigation-drawer>


      <!-- menu icon du profil dropdown -->
      <v-navigation-drawer
          v-model="drawer_accountIcon"
          absolute
          temporary

      >
        <!-- menu icon du profil si user connecté -->
        <v-list
            v-if="userConnected"
            nav
        >
          <v-list-item
              v-for="item in profilMenuItemsIfConnected"
              :key="item.title"
              :to="item.path">
            <v-list-tile-action>
              <v-icon>{{ item.icon }}</v-icon>
            </v-list-tile-action>
            <v-list-tile-content>{{ item.title }}</v-list-tile-content>
          </v-list-item>
        </v-list>

          <!-- menu icon du profil si user non connecté -->
          <v-list
              v-else
              nav
          >
          <v-list-item
              v-for="item in profilMenuItemsForAll"
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
    userConnected: false,

    menuItemsForAll: [
      {title: 'Accueil', path: '/', icon: 'home'},
      {title: 'Inscription', path: '/inscription', icon: 'lock_open'},
      {title: 'Connexion', path: '/connexion', icon: 'login'},
      {title: 'Recettes', path: '/recettes', icon: 'book'}
    ],
    menuItemsIfConnected: [
      {title: 'Accueil', path: '/', icon: 'home'},
      {title: 'Mes Recettes Favorites', path: '/recettesFavorites', icon: 'favorite'},
      {title: 'Mon Carnet de Recettes', path: '/carnetRecettes', icon: 'book'},
      {title: 'Mon Profil', path: '/profil', icon: 'face'},
      {title: 'Déconnexion', path: '/deconnexion', icon: 'logout'},
    ],
    profilMenuItemsForAll: [
      {title: 'Inscription', path: '/inscription', icon: 'face'},
      {title: 'Connexion', path: '/connexion', icon: 'lock_open'},
    ],
    profilMenuItemsIfConnected: [
      {title: 'Accueil', path: '/', icon: 'home'},
      {title: 'Mes Recettes Favorites', path: '/recettesFavorites', icon: 'favorite'},
      {title: 'Mon Carnet de Recettes', path: '/carnetRecettes', icon: 'book'},
      {title: 'Mon Profil', path: '/profil', icon: 'face'},
      {title: 'Déconnexion', path: '/deconnexion', icon: 'logout'},
    ],

  }),


}


</script>

<style scoped>

</style>