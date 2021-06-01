<template>
  <v-container>
    <v-row align="center" justify="center" v-for="(post, p) in posts" :key="p">
      <v-col cols="12" sm="8">
        <v-card>
          <v-card-title>
            <v-row>
              <v-col cols="12" sm="1">
                <v-avatar>
                  <v-img
                    :src="post.avatar"
                    max-height="50"
                    max-width="50"
                  ></v-img>
                </v-avatar>
              </v-col>
              <v-col cols="12" sm="8">
                <span class="mr-2">{{ post.name }}</span>
              </v-col>
            </v-row>
          </v-card-title>
          <v-card-text>
            <h3>{{ post.text }}</h3>
            <br />
            <v-img :src="post.img" max-height="1000"></v-img>
          </v-card-text>
          <v-divider></v-divider>
          <v-card-actions>
            <v-btn text>
              <v-icon class="mr-1">mdi-thumb-up-outline</v-icon> Like
            </v-btn>
            <v-btn text>
              <v-icon class="mr-1">mdi-comment-outline</v-icon> Comment
            </v-btn>
            <v-btn text>
              <v-icon class="mr-1">mdi-share-outline</v-icon> Share
            </v-btn>
          </v-card-actions>
          <v-divider></v-divider>
          <v-list v-for="(coment, com) in post.coments" :key="com">
            <v-row>
              <v-col cols="12" sm="1"></v-col>
              <v-col cols="12" sm="1"
                ><v-avatar>
                  <v-img
                    :src="coment.avatar"
                    max-height="50"
                    max-width="50"
                  ></v-img> </v-avatar
              ></v-col>
              <v-col cols="12" sm="9">
                <v-card elevation="3" outlined shaped>
                  <v-row>
                    <v-col cols="12" sm="12">
                      <v-card-title primary-title>
                        {{ coment.name }}
                      </v-card-title>
                      <v-card-text>
                        {{ coment.text }}
                      </v-card-text>
                      <v-divider></v-divider>
                      <v-card-actions>
                        <v-btn text>
                          <v-icon class="mr-1">mdi-thumb-up-outline</v-icon>
                          Like
                        </v-btn>
                        <v-btn text>
                          <v-icon class="mr-1">mdi-comment-outline</v-icon>
                          Reply
                        </v-btn>
                      </v-card-actions>
                    </v-col>
                  </v-row>
                </v-card>
              </v-col>
              <v-col cols="12" sm="1"></v-col>
            </v-row>
          </v-list>
          <v-divider></v-divider>
          <br />
          <v-row>
            <v-col cols="12" sm="1"></v-col>
            <v-col cols="12" sm="10">
              <v-text-field solo  append-icon="mdi-emoticon" append-outer-icon="mdi-send-outline" @click:append-outer="sendMessage" @click:append="emote"></v-text-field>
            </v-col>
            <v-col cols="12" sm="1"></v-col>
          </v-row>
        </v-card>
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
export default {
  name: "HelloWorld",
  data() {
    return {
      drawer: true,
      mini: true,
      posts: [
        {
          img:
            "https://abglt.org.br/wp-content/uploads/2020/10/wallpaper-pc1-scaled.jpg",
          name: "Roberto Carvalho",
          avatar:
            "https://i.pinimg.com/originals/32/38/6c/32386c72c7f2a8b5c1a10fc51c149cb1.jpg",
          text: "Look to horizon and make this your destiny.",
          coments: [
            {
              name: "Sarah Silva",
              avatar: "https://pbs.twimg.com/media/D8dDZukXUAAXLdY.jpg",
              text:
                "Coment TextComent TextComent Textnt TextComent TextComent TextComent Text"
            },
            {
              name: "Roberto Carvalho",
              avatar:
                "https://i.pinimg.com/originals/32/38/6c/32386c72c7f2a8b5c1a10fc51c149cb1.jpg",
              text:
                "Coment TextComent TextComent Textnt TextComent TextComent TextComent Text"
            },
            {
              name: "Mary Mine",
              avatar:
                "https://i.pinimg.com/originals/75/32/b3/7532b39f1013fb0c31da7025de5760e0.jpg",
              text:
                "Coment TextComent TextComent Textnt TextComent TextComent TextComent TextComent TextComent TextComent Textnt TextComent TextComent TextComent TextComent TextComent TextComent Textnt TextComent TextComent TextComent Text"
            }
          ]
        },
        {
          img:
            "https://i.pinimg.com/originals/0a/4d/cb/0a4dcb92fa2d3c601b58d72720d6bec4.jpg",
          name: "Mary Mine",
          avatar:
            "https://i.pinimg.com/originals/75/32/b3/7532b39f1013fb0c31da7025de5760e0.jpg",
          text: "My new picture, i loved this!!",
          coments: [
            {
              name: "Marco Oliveira",
              avatar:
                "https://v.cdn.vine.co/r/thumbs/7BBFD9F6741001009555343618048_14375368a64.3.4.mp4_.h0bQhclekDe.d93NrKYlAAnFPh_0MZ4ytGv6n2jVNfDUCsiiScO0NCYXe4Lt2ER.jpg?versionId=hxKBukyR5.deHYpG1a.qOKnPNUD5HgEN",
              text:
                "Coment TextComent TextComent Textnt TextComent TextComent TextComent Text"
            },
            {
              name: "Samuel muglia",
              avatar:
                "https://i.pinimg.com/236x/00/45/07/004507e436c0a869b821b53ab656c8e2.jpg",
              text:
                "Coment TextComent TextComent Textnt TextComent TextComent TextComent Text"
            },
            {
              name: "Hugel Virtanen",
              avatar:
                "https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcSC8RLe_OOzKzgfcfMly6PVFQf6h92g8gxpPQ&usqp=CAU",
              text:
                "Coment TextComent TextComent Textnt TextComent TextComent TextComent Text"
            }
          ]
        },
        {
          img:
            "https://steamuserimages-a.akamaihd.net/ugc/940586530515504757/CDDE77CB810474E1C07B945E40AE4713141AFD76/",
          name: "Sarah Silva",
          avatar: "https://pbs.twimg.com/media/D8dDZukXUAAXLdY.jpg",
          text:
            "Lorem ipsum dolor sit amet, consectetur adipiscing elit. Phasellus iaculis sed metus eget egestas. Curabitur magna elit, varius quis luctus in, blandit sit amet mi. Fusce pharetra mattis ornare. In nibh orci, sagittis non ultricies et, egestas vel nisl. In hac habitasse platea dictumst. Nunc leo metus, aliquet in risus et, volutpat suscipit massa. Pellentesque et dolor lacus. Praesent cursus ut dolor at blandit. Mauris volutpat porttitor varius. Nam vel pellentesque ante. Proin sit amet velit nunc. Ut vel tortor luctus, pretium felis vitae, pulvinar quam. Vivamus fermentum ligula quis feugiat tincidunt. Quisque tincidunt mi dapibus, sollicitudin ligula eget, egestas odio. Nullam luctus nisl volutpat neque ultricies ultrices. Sed condimentum nibh et tellus interdum, id varius nisi feugiat.",
          coments: [
            {
              name: "Samuel muglia",
              avatar:
                "https://i.pinimg.com/236x/00/45/07/004507e436c0a869b821b53ab656c8e2.jpg",
              text:
                "Coment TextComent TextComent Textnt TextComent TextComent TextComent Text"
            },
            {
              name: "Hugel Virtanen",
              avatar:
                "https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcSC8RLe_OOzKzgfcfMly6PVFQf6h92g8gxpPQ&usqp=CAU",
              text:
                "Coment TextComent TextComent Textnt TextComent TextComent TextComent Text"
            }
          ]
        },
        {
          img: "https://wallpapercave.com/wp/wp7864479.png",
          name: "Samuel muglia",
          avatar:
            "https://i.pinimg.com/236x/00/45/07/004507e436c0a869b821b53ab656c8e2.jpg",
          text:
            "Aliquam rhoncus turpis a neque malesuada scelerisque at in ante. Etiam dolor erat, mattis vitae mollis non, luctus nec libero. Nunc bibendum fringilla dui, et malesuada felis vestibulum ut. Morbi quis suscipit est. Sed quis aliquet sem. In hac habitasse platea dictumst. Vivamus imperdiet consectetur pellentesque.",
          coments: [
            {
              name: "Sarah Silva",
              avatar: "https://pbs.twimg.com/media/D8dDZukXUAAXLdY.jpg",
              text:
                "Lorem ipsum dolor sit amet, consectetur adipiscing elit. Phasellus iaculis sed metus eget egestas. Curabitur magna elit, varius quis luctus in, blandit sit amet mi. Fusce pharetra mattis ornare. In nibh orci, sagittis non ultricies et, egestas vel nisl. In hac habitasse platea dictumst. Nunc leo metus, aliquet in risus et, volutpat suscipit massa. Pellentesque et dolor lacus. Praesent cursus ut dolor at blandit. Mauris volutpat porttitor varius. Nam vel pellentesque ante. Proin sit amet velit nunc. Ut vel tortor luctus, pretium felis vitae, pulvinar quam. Vivamus fermentum ligula quis feugiat tincidunt. Quisque tincidunt mi dapibus, sollicitudin ligula eget, egestas odio."
            },
            {
              name: "Marco Oliveira",
              avatar:
                "https://v.cdn.vine.co/r/thumbs/7BBFD9F6741001009555343618048_14375368a64.3.4.mp4_.h0bQhclekDe.d93NrKYlAAnFPh_0MZ4ytGv6n2jVNfDUCsiiScO0NCYXe4Lt2ER.jpg?versionId=hxKBukyR5.deHYpG1a.qOKnPNUD5HgEN",
              text:
                "Coment TextComent TextComent Textnt TextComent TextComent TextComent Text"
            },
            {
              name: "Mary Mine",
              avatar:
                "https://i.pinimg.com/originals/75/32/b3/7532b39f1013fb0c31da7025de5760e0.jpg",
              text:
                "Coment TextComent TextComent Textnt TextComent TextComent TextComent Text"
            }
          ]
        },
        {
          img:
            "https://psxbrasil.com.br/wp-content/uploads/2020/09/TLOU-2-4K.jpg",
          name: "Marco Oliveira",
          avatar:
            "https://v.cdn.vine.co/r/thumbs/7BBFD9F6741001009555343618048_14375368a64.3.4.mp4_.h0bQhclekDe.d93NrKYlAAnFPh_0MZ4ytGv6n2jVNfDUCsiiScO0NCYXe4Lt2ER.jpg?versionId=hxKBukyR5.deHYpG1a.qOKnPNUD5HgEN",
          text: "<3",
          coments: [
            {
              name: "Roberto Carvalho",
              avatar:
                "https://i.pinimg.com/originals/32/38/6c/32386c72c7f2a8b5c1a10fc51c149cb1.jpg",
              text:
                "Coment TextComent TextComent Textnt TextComent TextComent TextComent Text"
            }
          ]
        }
      ]
    };
  },
  methods: {
      sendMessage: function(){
        console.log("sending")
      },
      emote: function(){
        console.log("emoting")
      }
    },
};
</script>
