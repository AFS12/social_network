<template>
  <v-app>
    <v-app-bar
      app
      color="grey darken-4"
      dark
    >
      <container class="d-flex align-center">
        <v-img
          alt="Vuetify Logo"
          class="shrink mr-2"
          contain
          src="https://cdn.vuetifyjs.com/images/logos/vuetify-logo-dark.png"
          transition="scale-transition"
          width="40"
        />
        <v-container>
          <h1>Social_Network</h1>
        </v-container>
      </container>

      <v-spacer></v-spacer>
      <v-tabs centered icons-and-text>
          <v-tab><v-icon>mdi-home</v-icon></v-tab>
          <v-tab><v-icon>mdi-monitor-dashboard</v-icon></v-tab>
          <v-tab><v-icon>mdi-store</v-icon></v-tab>
          <v-tab><v-icon>mdi-account-group</v-icon></v-tab>
          <v-tab><v-icon>mdi-gamepad</v-icon></v-tab>
        </v-tabs>
      <v-spacer></v-spacer>
      <v-btn
        href="https://github.com/vuetifyjs/vuetify/releases/latest"
        target="_blank"
        rounded
        text
      >
        <v-img src="https://cdn.vuetifyjs.com/images/logos/vuetify-logo-dark.png" width="30"></v-img>
        <span class="mr-2">Arthur</span>
      </v-btn>
      <v-btn fab small rounded color="grey darken-3">
         <v-icon>mdi-dots-grid</v-icon>
      </v-btn>
      -
      <v-btn fab small rounded color="grey darken-3">
        <v-icon>mdi-facebook-messenger</v-icon>
      </v-btn>
      -
      <v-btn fab small rounded color="grey darken-3">
        <v-icon>mdi-bell</v-icon>
      </v-btn>
      -
      <v-btn fab small rounded color="grey darken-3">
        <v-icon>mdi-menu-down</v-icon>
      </v-btn>
    </v-app-bar>

    <v-main>
      <HelloWorld/>
    </v-main>
  </v-app>
</template>

<script>
import HelloWorld from './components/HelloWorld';

export default {
  name: 'App',

  components: {
    HelloWorld,
  },

  data: () => ({
    //
  }),
};
</script>

<style>
  #Search{
    padding-top: 10px;
  }
</style>