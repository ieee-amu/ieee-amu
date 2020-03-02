<template>
  <v-app>
    <v-app-bar fixed app dark>
      <v-btn :to="`/`" depressed>
        <v-toolbar-title v-text="title" />
      </v-btn>
      <v-spacer />
      <div>
        <v-btn :to="`/#about-us`" icon style="margin-right: 0.5em">
          ABOUT
        </v-btn>
        <v-btn :to="`/team`" icon style="margin-right: 0.5em">
          TEAM
        </v-btn>
        <v-btn :to="`/blog`" icon style="margin-right: 0.5em">
          BLOG &nbsp;
        </v-btn>
        <v-btn :to="`/contact`" icon style="margin-right: 0.5em">
          CONTACT
        </v-btn>
      </div>
    </v-app-bar>
    <v-content>
      <v-container>
        <nuxt />
      </v-container>
    </v-content>
    <v-footer :fixed="fixed" app dark padless>
      <v-card class="flex" flat tile>
        <v-card-title class="black">
          <strong class="subheading">Get connected with us!</strong>

          <v-spacer></v-spacer>

          <v-btn v-for="icon in icons" :key="icon" class="mx-4" dark icon>
            <v-icon size="24px">{{ icon }} </v-icon>
          </v-btn>
        </v-card-title>

        <v-card-text class="py-2 white--text text-center">
          {{ new Date().getFullYear() }} — <strong>IEEE AMU</strong>
        </v-card-text>
      </v-card>
    </v-footer>
  </v-app>
</template>

<script>
export default {
  data() {
    return {
      icons: [
        'mdi-facebook',
        'mdi-twitter',
        'mdi-google-plus',
        'mdi-linkedin',
        'mdi-instagram'
      ],
      title: 'IEEE AMU'
    }
  }
}
</script>
