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
        <v-btn :to="`/#about-us`">
          <v-icon> mdi-home </v-icon>&nbsp; ABOUT &nbsp;</v-btn
        >
        <v-btn :to="`/team`">
          <v-icon> mdi-account </v-icon>&nbsp; TEAM &nbsp;</v-btn
        >
        <v-btn :to="`/blog`">
          <v-icon> mdi-book </v-icon>&nbsp; BLOG &nbsp;</v-btn
        >
        <v-btn :to="`/contact`">
          <v-icon> mdi-contacts </v-icon>&nbsp; CONTACT &nbsp;</v-btn
        >
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
        <v-list-item
          v-for="item in navItems"
          :key="item.title"
          :to="item.link"
          link
        >
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
          &copy; {{ new Date().getFullYear() }} — <strong>IEEE AMU</strong>
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
      icons: ['mdi-facebook', 'mdi-instagram'],
      title: 'IEEE AMU',
      navItems: [
        { title: 'About', icon: 'mdi-home', link: '/#about-us' },
        { title: 'Team', icon: 'mdi-account', link: '/team' },
        { title: 'Blog', icon: 'mdi-book', link: '/blog' },
        { title: 'Contact Us', icon: 'mdi-contacts', link: '/contact' }
      ]
    }
  }
}
</script>
