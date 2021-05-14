<template>
  <v-container fluid>
    <v-layout row wrap>
      <v-flex xs12 class="text-xs-center" mt-5>
        <h1>Connexion</h1>
      </v-flex>
      <v-flex xs12 sm6 offset-sm3 mt-3>
        <v-form>
          <v-layout column>
            <v-flex>
              <v-text-field

                  name="email"
                  label="Email"
                  id="email"
                  type="email"
                  required
                  :rules="emailRules"
              ></v-text-field>
            </v-flex>
            <v-flex>
              <v-text-field
                  name="mot de passe"
                  label="Mot de passe"
                  id="password"
                  type="password"
                  required
                  autocomplete="new-password"
                  :rules="[rules.required]"
              ></v-text-field>
            </v-flex>
            <v-flex class="text-xs-center" mt-5>
              <v-btn rounded color="#85CB85" class="white--text"  type="submit">Se connecter</v-btn>
            </v-flex>
          </v-layout>
        </v-form>
      </v-flex>
    </v-layout>
  </v-container>
</template>

<script>
export default {
  name: "Connexion",

  data: () => ({

    emailRules: [
      v => !!v || "Required",
      v => /.+@.+\..+/.test(v) || "E-mail must be valid"
    ],
    rules: {
      required: value => !!value || "Required"
    }


  })

};
</script>


<style scoped>


</style>