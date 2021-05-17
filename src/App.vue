<template>
  <v-app>
    <v-container fluid>
      <v-app-bar app color="grey darken-4" dark fixed>

        <v-tabs centered icons-and-text>
          <v-tab><v-icon>mdi-home</v-icon></v-tab>
          <v-tab><v-icon>mdi-monitor-dashboard</v-icon></v-tab>
          <v-tab><v-icon>mdi-store</v-icon></v-tab>
          <v-tab><v-icon>mdi-account-group</v-icon></v-tab>
          <v-tab><v-icon>mdi-gamepad</v-icon></v-tab>
        </v-tabs>
        <v-spacer></v-spacer>
      </v-app-bar>
    </v-container>
    <v-navigation-drawer fixed app v-model="drawer" :mini-variant.sync="mini" left>
      <v-list-item class="grey darken-4" dark>
        <v-list-item-content color="primary">
          <v-list-item-title class="title">
            <v-btn
              rounded
              outlined
              height="40"
              text
            >
              <v-img
                src="https://cdn.vuetifyjs.com/images/logos/vuetify-logo-dark.png"
                width="25"
              ></v-img>
              <span class="mr-2 ">Arthur Ayres</span>
            </v-btn>
          </v-list-item-title>
        </v-list-item-content>
      </v-list-item>

      <v-divider></v-divider>

      <v-list dense nav>
        <v-list-item v-for="item in items" :key="item.title" link>
          <v-list-item-icon>
            <v-icon>{{ item.icon }}</v-icon>
          </v-list-item-icon>

          <v-list-item-content>
            <v-list-item-title>{{ item.title }}</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>

    <v-navigation-drawer
      fixed
      app
      v-model="drawer"
      :mini-variant.sync="mini"
      right
    >
      <v-list-item class="grey darken-4">
        <v-list-item-content color="primary">
          <v-list-item-title class="title">
            <v-row>
              <v-col cols="12" md="3">
                <v-btn fab small rounded elevation="0">
                  <v-icon>mdi-dots-grid</v-icon>
                </v-btn>
              </v-col>
              <v-col cols="12" md="3">
                <v-btn fab small rounded elevation="0">
                  <v-icon>mdi-facebook-messenger</v-icon>
                </v-btn>
              </v-col>
              <v-col cols="12" md="3">
                <v-btn fab small rounded elevation="0">
                  <v-icon>mdi-bell</v-icon>
                </v-btn>
              </v-col>
              <v-col cols="12" md="3">
                <v-btn fab small rounded elevation="0">
                  <v-icon>mdi-menu-down</v-icon>
                </v-btn>
              </v-col>
            </v-row>
          </v-list-item-title>
        </v-list-item-content>
      </v-list-item>

      <v-divider></v-divider>

      <v-list dense nav>
        <v-list-item v-for="item in items" :key="item.title" link>
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
      <v-container fluid> </v-container>

      <HelloWorld />
    </v-main>
  </v-app>
</template>

<script>
import HelloWorld from "./components/HelloWorld";

export default {
  name: "App",

  components: {
    HelloWorld
  },

  data() {
    return {
      items: [
        { title: "Dashboard", icon: "mdi-view-dashboard" },
        { title: "Photos", icon: "mdi-image" },
        { title: "About", icon: "mdi-help-box" }
      ],
      right: null
    };
  }
};
</script>

<style>
#Search {
  padding-top: 10px;
}
</style>