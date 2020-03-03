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

    <spacer gap="10" />

    <v-footer :fixed="fixed" app dark padless>
      <v-card class="flex" flat tile>
        <v-card-title class="grey darken-4">
          <strong class="subheading">Connect with us!</strong>

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
import Spacer from '@/components/Spacer'

export default {
  components: {
    Spacer
  },
  data() {
    return {
      drawer: false,
      icons: [
        'mdi-facebook',
        'mdi-twitter',
        'mdi-google-plus',
        'mdi-linkedin',
        'mdi-instagram'
      ],
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
