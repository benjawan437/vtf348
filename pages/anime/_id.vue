<template>
  <div>
    <h1>{{ title }}</h1>
    <v-row cols="12">
      <v-col class="md-6 ml-6">
        <v-img :src="img" height="550" width="550"></v-img>
      </v-col>
      <v-col class="md-6 mr-6">
        There are a total number of episodes : {{ ep }}
        <br />
        type : {{ type }} | score : {{ sc }}
        <br />
        {{ syn }} <br />
      </v-col>
    </v-row>
  </div>
</template>

<script>
export default {
  data() {
    return {
      title: this.$route.params.id.title,
      syn: this.$route.params.id.synopsis,
      img: this.$route.params.id.image_url,
      ep: this.$route.params.id.episodes,
      sc: this.$route.params.id.score,
      type: this.$route.params.id.type,
    }
    // console.log(this.$route.parms.id.synopsis)
  },
}
</script>
