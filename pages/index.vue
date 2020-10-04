<template>
  <v-parallax
    src="https://wallpaperset.com/w/full/9/4/d/38453.jpg"
    height="auto"
  >
    <v-row justify="center" align="center">
      <v-col cols="12" sm="8" md="6">
        <div align="center">
          <vuetify-logo />
        </div>
        <v-card class="mt-5">
          <v-card-title class="headline">
            Welcome to the world of anime
          </v-card-title>
          <v-card-text>
            <p>
              Our website contains a list of Knowledge of many anime on this
              world.
            </p>
            <p>Have fun with our world Thank you for visiting.</p>
            <p>Good luck!!</p>
            <div class="text-xs-right">
              <em><small>&mdash; STAMP</small></em>
            </div>
            <hr class="my-3" />
            <br />
          </v-card-text>
          <v-card-actions>
            <v-spacer />
            <v-btn color="amber darken-4" nuxt to="/anime"> Continue </v-btn>
          </v-card-actions>
        </v-card>
      </v-col>
    </v-row>
  </v-parallax>
</template>

<script>
import VuetifyLogo from '~/components/VuetifyLogo.vue'

export default {
  components: {
    VuetifyLogo,
  },
}
</script>
