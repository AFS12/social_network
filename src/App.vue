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
    <v-navigation-drawer fixed app left>
      <v-list-item class="grey darken-4" dark>
        <v-list-item-content color="primary">
          <v-list-item-title class="title">
            <v-btn rounded outlined height="40" text>
              <v-avatar>
                <v-img
                  src="https://scontent.fmcz3-1.fna.fbcdn.net/v/t1.6435-9/82493379_3529103920494983_8465647889245274112_n.jpg?_nc_cat=110&ccb=1-3&_nc_sid=09cbfe&_nc_eui2=AeEADBnWqpwPLSavBS35YwmwaHmnngysQmpoeaeeDKxCamLd5rHny-zLsFjH9xweygwB3INDOgnX9S0soMHtfivw&_nc_ohc=D9MDAce1smQAX_ZIhNX&_nc_ht=scontent.fmcz3-1.fna&oh=5922a9e6ab2492e4abc8945acf270bcc&oe=60DBCEF6"
                  max-height="35"
                  max-width="35"
                ></v-img>
              </v-avatar>
              <span class="mr-2 ">Arthur Ayres</span>
            </v-btn>
          </v-list-item-title>
        </v-list-item-content>
      </v-list-item>

      <v-divider></v-divider>

      <v-list dense nav>
        <v-list-item v-for="(item, i) in items" :key="i" link>
          <v-list-item-icon>
            <v-icon>{{ item.icon }}</v-icon>
          </v-list-item-icon>

          <v-list-item-content>
            <v-list-item-title>{{ item.title }}</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>

    <v-navigation-drawer fixed app right>
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
                    <v-btn
                      fab
                      small
                      rounded
                      elevation="0"
                      v-bind="attrs"
                      v-on="on"
                    >
                      <v-icon>mdi-bell</v-icon>
                    </v-btn>
                  </template>
                  <v-list>
                    <v-list-item
                      v-for="(notfication, not) in notfications"
                      :key="not"
                    >
                      <v-list-item-avatar>
                        <v-img :src="notfication.avatar"></v-img>
                      </v-list-item-avatar>
                      <v-list-item-title>{{
                        notfication.name
                      }}</v-list-item-title>
                      <br />
                      <v-list-item-subtitle>{{
                        notfication.title
                      }}</v-list-item-subtitle>
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
        <v-list-item v-for="(friend, f) in friends" :key="f" link>
          <v-list-item-avatar>
            <v-img :src="friend.avatar"></v-img>
          </v-list-item-avatar>

          <v-list-item-content>
            <v-list-item-title>{{ friend.title }}</v-list-item-title>
          </v-list-item-content>

          <v-badge bottom :color="friend.status" dot overlap></v-badge>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>
    <v-main>
      <v-row>
        <v-spacer></v-spacer>
        <v-cols>
          <v-avatar size="75">
            <v-img
              src="https://scontent.fmcz3-1.fna.fbcdn.net/v/t1.6435-9/82493379_3529103920494983_8465647889245274112_n.jpg?_nc_cat=110&ccb=1-3&_nc_sid=09cbfe&_nc_eui2=AeEADBnWqpwPLSavBS35YwmwaHmnngysQmpoeaeeDKxCamLd5rHny-zLsFjH9xweygwB3INDOgnX9S0soMHtfivw&_nc_ohc=D9MDAce1smQAX_ZIhNX&_nc_ht=scontent.fmcz3-1.fna&oh=5922a9e6ab2492e4abc8945acf270bcc&oe=60DBCEF6"
              max-height="100"
              max-width="100"
            ></v-img>
          </v-avatar>
          <h5>Arthur Ayres</h5>
        </v-cols>
        <v-cols v-for="(friend, f) in friends" :key="f">
          <v-avatar size="75" >
            <v-img
              :src= friend.avatar
              max-height="100"
              max-width="100"
            ></v-img>
          </v-avatar>
          <h5>{{friend.title}}</h5>
        </v-cols>
        <v-spacer></v-spacer>
      </v-row>
      <br>
      <v-divider></v-divider>
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
        { title: "Friends", icon: "mdi-account-multiple" },
        { title: "Groups", icon: "mdi-account-group" },
        { title: "Saved", icon: "mdi-content-save" },
        { title: "Pages", icon: "mdi-flag-variant" },
        { title: "Photos", icon: "mdi-image" },
        { title: "About", icon: "mdi-help-box" }
      ],
      friends: [
        {
          status: "green",
          title: "Marco Oliveira",
          avatar:
            "https://v.cdn.vine.co/r/thumbs/7BBFD9F6741001009555343618048_14375368a64.3.4.mp4_.h0bQhclekDe.d93NrKYlAAnFPh_0MZ4ytGv6n2jVNfDUCsiiScO0NCYXe4Lt2ER.jpg?versionId=hxKBukyR5.deHYpG1a.qOKnPNUD5HgEN"
        },
        {
          status: "red",
          title: "Sarah Silva",
          avatar: "https://pbs.twimg.com/media/D8dDZukXUAAXLdY.jpg"
        },
        {
          status: "green",
          title: "Roberto Carvalho",
          avatar:
            "https://i.pinimg.com/originals/32/38/6c/32386c72c7f2a8b5c1a10fc51c149cb1.jpg"
        },
        {
          status: "grey",
          title: "Hugel Virtanen",
          avatar:
            "https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcSC8RLe_OOzKzgfcfMly6PVFQf6h92g8gxpPQ&usqp=CAU"
        },
        {
          status: "green",
          title: "Samuel muglia",
          avatar:
            "https://i.pinimg.com/236x/00/45/07/004507e436c0a869b821b53ab656c8e2.jpg"
        },
        {
          status: "red",
          title: "Mary Mine",
          avatar:
            "https://i.pinimg.com/originals/75/32/b3/7532b39f1013fb0c31da7025de5760e0.jpg"
        }
      ],
      notfications: [
        {
          title: "Comented on your post",
          avatar: "https://pbs.twimg.com/media/D8dDZukXUAAXLdY.jpg",
          name: "Sarah Silva"
        },
        {
          title: "Liked Your post",
          avatar: "https://pbs.twimg.com/media/D8dDZukXUAAXLdY.jpg",
          name: "Sarah Silva"
        },
        {
          title: "Comented on your post",
          avatar:
            "https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcSC8RLe_OOzKzgfcfMly6PVFQf6h92g8gxpPQ&usqp=CAU",
          name: "Hugel Virtanen"
        },
        {
          title: "Mentioned you on publication",
          avatar:
            "https://i.pinimg.com/236x/00/45/07/004507e436c0a869b821b53ab656c8e2.jpg",
          name: "Samuel muglia"
        }
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