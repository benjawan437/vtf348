<template>
  <v-parallax
    src="https://wallpaperset.com/w/full/c/5/8/200310.jpg"
    height="1080"
    width="1920"
    jumbotron
  >
    <v-layout>
      <v-flex class="text-center mb-2">
        <img
          src="https://cdn.shopify.com/s/files/1/0283/4240/t/8/assets/logo.png?v=1384290359576997508"
          alt="Vuetify.js"
          width="660"
        />
        <v-container class="center"
          ><input type="text" class="datee" v-model="keyword" />
          <button class="button" @click="searchData()">
            Search
          </button></v-container
        >
      </v-flex>
    </v-layout>
    <v-row justify="space-around" v-if="result">
      <v-col cols="12" sm="10" md="12">
        <v-chip-group multiple active-class="primary--text">
          <v-card
            class="mx-auto ml-4"
            max-width="400"
            v-for="re in result"
            :key="re.mal_id"
          >
            <v-img :src="re.image_url" height="auto"></v-img>
            <v-card-title> {{ re.title }} </v-card-title>
            <v-card-actions>
              <v-btn color="deep-purple lighten-2" text
                ><nuxt-link :to="{ name: 'anime-id', params: { id: re } }">
                  See more</nuxt-link
                ></v-btn
              >
            </v-card-actions>
          </v-card>
        </v-chip-group>
      </v-col>
    </v-row>
  </v-parallax>
</template>
<script>
import axios from 'axios'
export default {
  data() {
    return {
      result: null,
      keyword: '',
    }
  },
  methods: {
    searchData() {
      axios
        .get(
          'https://api.jikan.moe/v3/search/anime?q=' + this.keyword + '&page=1'
        )
        .then((response) => {
          this.result = response.data.results
        })
        .catch((err) => {
          console.log(err)
        })
    },
  },
}
</script>
<style>
.sea {
  width: 30rem;
}
.button {
  background-color: rgb(243, 190, 109);
  border: none;
  color: rgb(238, 105, 28);
  padding: 5px 5px 5px 5px;
  text-align: center;
  display: inline-block;
  margin: 10px 5px;
  font-size: 2rem;
  cursor: pointer;
  border-radius: 12px;
  border: 0.5px solid rgb(253, 182, 101);
  width: 10rem;
}
button:hover {
  color: rgb(240, 66, 13);
  border: 0.5px solid rgba(0, 0, 0, 0.596);
  background-color: rgba(0, 0, 0, 0.658);
}
.bo {
  color: white;
  font-size: 50px;
}
.datee {
  border-radius: 8px;
  padding: 12px;
  border: 2px solid #000000;
  font-size: 20px;
  width: 30rem;
  background-color: white;
}
.h {
  font-size: 1.25rem;
}
</style>
