<template>
  <v-container>
    <v-row align="center" justify="center" v-for="index in 5" :key="index">
      <v-col cols="12" sm="8">
        <v-card>
          <v-card-title>
            <v-img
              src="https://cdn.vuetifyjs.com/images/logos/vuetify-logo-dark.png"
              max-height="50"
              max-width="50"
            ></v-img>
            <span class="mr-2 ">Arthur Ayres</span>
          </v-card-title>
          <v-card-text>
            <h3>ALGUMA PUB</h3>
            <br>
            <v-img
              src="https://abglt.org.br/wp-content/uploads/2020/10/wallpaper-pc1-scaled.jpg"
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
      numbers: [ 1, 2, 3, 4, 5 ]
    };
    
  }
};
</script>
