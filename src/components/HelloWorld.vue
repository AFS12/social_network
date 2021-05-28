<template>
  <v-container>
    <v-row align="center" justify="center" v-for="index in posts" :key="index">
      <v-col cols="12" sm="8">
        <v-card>
          <v-card-title>
            <v-img
              src="https://cdn.vuetifyjs.com/images/logos/vuetify-logo-dark.png"
              max-height="50"
              max-width="50"
            ></v-img>
            <span class="mr-2 ">{{index.name}}</span>
          </v-card-title>
          <v-card-text>
            <h3>ALGUMA PUB</h3>
            <br>
            <v-img
              :src= index.img
              max-height="1000"
            ></v-img>
          </v-card-text>
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
          img: 'https://abglt.org.br/wp-content/uploads/2020/10/wallpaper-pc1-scaled.jpg',
          name: 'Arthur Ayres',
        }, 
        {
          img: 'https://i.pinimg.com/originals/0a/4d/cb/0a4dcb92fa2d3c601b58d72720d6bec4.jpg',
          name: 'Julia Goncalves',
        }, 
        {
          img: 'https://steamuserimages-a.akamaihd.net/ugc/940586530515504757/CDDE77CB810474E1C07B945E40AE4713141AFD76/',
          name: 'Juia Do Carmo',
        }, 
        {
          img: 'https://wallpapercave.com/wp/wp7864479.png',
          name: 'Paçoca Mendonça',
        }, 
        {
          img: 'https://psxbrasil.com.br/wp-content/uploads/2020/09/TLOU-2-4K.jpg',
          name: 'GameShop',
        } ]
    };
    
  }
};
</script>
