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
    <v-footer :fixed="fixed" app>
      <span>&copy; 2020</span>
    </v-footer>
  </v-app>
</template>

<script>
export default {
  data() {
    return {
      title: 'IEEE AMU'
    }
  }
}
</script>
