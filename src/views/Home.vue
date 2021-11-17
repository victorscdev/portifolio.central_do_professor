<template>
  <v-container>
    <v-row>
      <v-col cols="12">
        <h1>Bem Vindo!</h1>
        <v-btn
          @click.prevent="signOut"
          color="danger"
          elevation="4"
        >
        Sair
        </v-btn>
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
  import firebase from "firebase/app"

  export default {
    name: 'Home',
    data: () => ({
      
    }),
    methods: {
      signOut() {
        firebase
        .auth()
        .signOut()
        .then(() => {
          this.$router.replace('/login')
        })
      }
    }
  }
</script>
