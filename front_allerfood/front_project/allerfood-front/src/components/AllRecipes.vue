<template>
  <v-card
      class="ma-4 pa-2"
      elevation="4"
      loading = false;
      outlined
      shaped
      max-width="374"
  >
    <v-img
        src="https://img.cuisineaz.com/660x660/2015-09-14/i79805-omelette-aux-champignons-de-paris.jpg"
        height="200px"
    ></v-img>

    <v-card-title>
      {{ titre }}
    </v-card-title>

    <v-card-subtitle>
      {{ sousTitre }}
    </v-card-subtitle>

    <div>
      <v-icon>mdi-timer-outline</v-icon>
      {{ tempsDePreparation }}
      {{ favorite }}
    </div>

    <v-btn
        class="mx-2"
        small
        icon
        :color="getIconColor"

        @click="favorite = !favorite"
    >
      <v-icon>mdi-heart</v-icon>
    </v-btn>


    <v-icon
        dense
        color="blue darken-2"
    >mdi-Accept</v-icon>

  </v-card>
</template
    >

<script>
export default {
  name: "AllRecipes.vue",
  props: ['titre', 'sousTitre', 'tempsDePreparation', 'favorite'],

  computed: {
    getIconColor() {
      return this.favorite ? 'pink' : 'gray';
    }
  }
}

</script>

<style scoped>

</style>
