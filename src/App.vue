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
                <v-menu offset-y>
                  <template v-slot:activator="{ on, attrs }">
                    <v-btn fab small rounded elevation="0" v-bind="attrs" v-on="on">
                      <v-icon>mdi-bell</v-icon>
                    </v-btn>
                  </template>
                  <v-list>
                    <v-list-item
                      v-for="(item, index) in notfications"
                      :key="index"
                    >
                      <v-list-item-avatar>
                        <v-img :src="item.avatar"></v-img>
                      </v-list-item-avatar>
                      <v-list-item-title>{{ item.name }}</v-list-item-title>
                      <br>
                      <v-list-item-subtitle>{{ item.title }}</v-list-item-subtitle>
                          <v-divider></v-divider>
                    </v-list-item>
                  </v-list>
                </v-menu>
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
        <v-list-item v-for="item in friends" :key="item.title" link>
          
          <v-list-item-avatar>
            <v-img :src="item.avatar"></v-img>
          </v-list-item-avatar>

          <v-list-item-content>
            <v-list-item-title>{{ item.title }}</v-list-item-title>
          </v-list-item-content>

          <v-badge
            bottom
            :color = item.status
            dot
            overlap
          ></v-badge>
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
      friends: [
        { status: "green", title: "Marco Oliveira", avatar: "https://v.cdn.vine.co/r/thumbs/7BBFD9F6741001009555343618048_14375368a64.3.4.mp4_.h0bQhclekDe.d93NrKYlAAnFPh_0MZ4ytGv6n2jVNfDUCsiiScO0NCYXe4Lt2ER.jpg?versionId=hxKBukyR5.deHYpG1a.qOKnPNUD5HgEN" },
        { status: "red", title: "Sarah Silva", avatar: "https://pbs.twimg.com/media/D8dDZukXUAAXLdY.jpg" },
        { status: "green", title: "Roberto Carvalho", avatar: "https://i.pinimg.com/originals/32/38/6c/32386c72c7f2a8b5c1a10fc51c149cb1.jpg" },
        { status: "grey", title: "Hugel Virtanen", avatar: "https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcSC8RLe_OOzKzgfcfMly6PVFQf6h92g8gxpPQ&usqp=CAU" },
        { status: "green", title: "Samuel muglia", avatar: "https://i.pinimg.com/236x/00/45/07/004507e436c0a869b821b53ab656c8e2.jpg" },
        { status: "red", title: "Mary Mine", avatar: "https://i.pinimg.com/originals/75/32/b3/7532b39f1013fb0c31da7025de5760e0.jpg" },
      ],
      notfications: [
        { title: 'Comented on your post', avatar: "https://pbs.twimg.com/media/D8dDZukXUAAXLdY.jpg", name: "Sarah Silva" },
        { title: 'Liked Your post', avatar: "https://pbs.twimg.com/media/D8dDZukXUAAXLdY.jpg", name: "Sarah Silva"},
        { title: 'Comented on your post', avatar: "https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcSC8RLe_OOzKzgfcfMly6PVFQf6h92g8gxpPQ&usqp=CAU", name: "Hugel Virtanen" },
        { title: 'Mentioned you on publication', avatar: "https://i.pinimg.com/236x/00/45/07/004507e436c0a869b821b53ab656c8e2.jpg", name: "Samuel muglia" },
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