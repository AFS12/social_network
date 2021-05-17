<template>
  <v-app>
    <v-container fluid>
      <v-app-bar
      app
      color="grey darken-4"
      dark
      fixed
    >
      <container class="d-flex align-center">
        
        <v-container>
          
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
    </v-container>
    <v-navigation-drawer  fixed app v-model='drawer' :mini-variant.sync="mini">
      <v-list-item>
        <v-list-item-content color="primary">
          <v-list-item-title class="title">
            <v-img
          alt="Vuetify Logo"
          class="shrink mr-2"
          contain
          src="https://cdn.vuetifyjs.com/images/logos/vuetify-logo-dark.png"
          transition="scale-transition"
          width="30"
        />
          </v-list-item-title>
        </v-list-item-content>
      </v-list-item>

      <v-divider></v-divider>

      <v-list
        dense
        nav
      >
        <v-list-item
          v-for="item in items"
          :key="item.title"
          link
        >
          <v-list-item-icon>
            <v-icon>{{ item.icon }}</v-icon>
          </v-list-item-icon>

          <v-list-item-content>
            <v-list-item-title>{{ item.title }}</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>
    <v-main>
      <v-container fluid>
       

      </v-container>
      
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

  data () {
    return{
      items: [
          { title: 'Dashboard', icon: 'mdi-view-dashboard' },
          { title: 'Photos', icon: 'mdi-image' },
          { title: 'About', icon: 'mdi-help-box' },
        ],
        right: null,
    }
  },
};
</script>

<style>
  #Search{
    padding-top: 10px;
  }
</style>