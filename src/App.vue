<template>
  <v-app>
    <v-app-bar app color="red darken-3">

      <v-btn color="success" class="mr-10" :to="{name:'Home'}"><h1>Fabien En Forme</h1></v-btn>
      
      <v-btn color="success" :to="{name:'About'}">About</v-btn>

      <v-spacer></v-spacer>

      <v-btn color="success" :to="{name:'Connexion'}">Connexion</v-btn>

    </v-app-bar>

    <v-main>
      <v-container>
        
        <router-view/>

      </v-container>
    </v-main>
  </v-app>
</template>

<script>

</script>

<style lang="scss">

</style>