<template>

    <v-container fluid>
      <v-layout row wrap>
        <v-flex xs12 class="text-xs-center" mt-5>
          <h1>Inscription</h1>
        </v-flex>
        <v-flex xs12 sm6 offset-sm3 mt-3>
          <form>
            <v-layout column>
              <v-flex>

                <v-text-field
                    v-model="identifiant"
                    name="pseudo"
                    label="Identifiant"
                    id="pseudo"
                    type="text"
                    required
                    :rules="identifiantRules"

                ></v-text-field>
              </v-flex>
              <v-flex>
                <v-text-field
                    v-model="mail"
                    name="email"
                    label="Email"
                    id="email"
                    type="email"
                    required
                    :rules="loginEmailRules"
                  ></v-text-field>
              </v-flex>
              <v-flex>
                <v-text-field
                    v-model="mdp"
                    name="password"
                    label="Mot de Passe"
                    id="password"
                    type="password"
                    required
                    autocomplete="new-password"
                    :rules="[rules.required, rules.min]"></v-text-field>
              </v-flex>
              <v-flex>
                <v-text-field
                    v-model="confirmMdp"
                    name="confirmPassword"
                    label="Confirm Password"
                    id="confirmPassword"
                    type="password"
                    required

                ></v-text-field>
              </v-flex>
              <v-flex class="text-xs-center" mt-5>
                <v-btn rounded color="#85CB85" class="white--text" type="submit">S'inscrire</v-btn>
              </v-flex>
            </v-layout>
          </form>
        </v-flex>
      </v-layout>
    </v-container>
  </template>

  <script>
    export default {
      name :"Inscription",

      data: () => ({
        identifiant: "",
        mail: "",
        mdp: "",
        confirmMdp: "",
        identifiantRules : [
          v => !!v || "Champs requis",
        ],
        loginEmailRules: [
          v => !!v || "Champs requis",
          v => /.+@.+\..+/.test(v) || "E-mail non-valide"
        ],
        emailRules: [
          v => !!v || "Required",
          v => /.+@.+\..+/.test(v) || "E-mail non-valide"
        ],

        rules: {
          required: value => !!value || "Champs requis",
          min: v => (v && v.length >= 8) || "Minimum 8 caractères"

        },

      })
    };
  </script>


<style scoped>





</style>