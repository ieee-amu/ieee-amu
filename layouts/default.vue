<template>
  <v-app>
    <v-app-bar fixed app dark>
      <v-app-bar-nav-icon
        @click.stop="drawer = !drawer"
        class="hidden-md-and-up"
      ></v-app-bar-nav-icon>
      <v-btn :to="`/`" depressed>
        <v-toolbar-title v-text="title" />
      </v-btn>
      <v-spacer />
      <div class="hidden-sm-and-down">
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

    <v-navigation-drawer v-model="drawer" app temporary>
      <v-list-item>
        <v-list-item-content>
          <v-list-item-title>AMU IEEE Chapter</v-list-item-title>
        </v-list-item-content>
      </v-list-item>

      <v-divider></v-divider>

      <v-list dense>
        <v-list-item v-for="item in navItems" :key="item.title" link>
          <v-list-item-icon>
            <v-icon>{{ item.icon }}</v-icon>
          </v-list-item-icon>
          <v-list-item-content>
            <v-list-item-title>{{ item.title }}</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>

    <v-content>
      <v-container>
        <nuxt />
      </v-container>
    </v-content>
    <v-footer :fixed="fixed" app dark prominent id="test">
      <v-row justify="center">
        <v-col cols="12">
          <v-row justify="center">
            <span>&copy; IEEE AMU 2020</span>
          </v-row>
        </v-col>
      </v-row>
    </v-footer>
  </v-app>
</template>

<script>
export default {
  data() {
    return {
      drawer: false,
      icons: ['mdi-facebook', 'mdi-instagram'],
      title: 'IEEE AMU',
      navItems: [
        { title: 'About', icon: 'mdi-home' },
        { title: 'Team', icon: 'mdi-account' },
        { title: 'Blog', icon: 'mdi-book' },
        { title: 'Contact Us', icon: 'mdi-contacts' }
      ]
    }
  }
}
</script>
<style scoped>
#test {
  padding-top: 20px;
}
</style>
