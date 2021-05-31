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
        { status: "red", title: "Mary Mine", avatar: "data:image/jpeg;base64,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" },
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