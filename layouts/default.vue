<template>
  <v-app>
    <v-app-bar fixed app dark>
      <v-app-bar-nav-icon
        class="hidden-md-and-up"
        @click.stop="drawer = !drawer"
      ></v-app-bar-nav-icon>
      <v-btn :to="`/`" depressed width="250px" height="50px">
        <v-img
          src="https://firebasestorage.googleapis.com/v0/b/ieee-amu.appspot.com/o/logo.svg?alt=media&token=4f818ffd-d53e-463b-ada8-78b568e323cd"
          width="250px"
          height="50px"
        ></v-img>
      </v-btn>
      <v-spacer />
      <div class="hidden-sm-and-down">
        <v-btn icon @click="changeMode">
          <v-icon>mdi-weather-sunny </v-icon>
        </v-btn>
        <v-btn text small to="/#about-us">
          <v-icon> mdi-home </v-icon>&nbsp; ABOUT &nbsp;
        </v-btn>
        <v-btn text small to="/team">
          <v-icon> mdi-account </v-icon>&nbsp; TEAM &nbsp;
        </v-btn>
        <v-btn text small to="/blog">
          <v-icon> mdi-book </v-icon>&nbsp; BLOG &nbsp;
        </v-btn>
        <v-btn text small to="/contact">
          <v-icon> mdi-contacts </v-icon>&nbsp; CONTACT &nbsp;
        </v-btn>
      </div>
    </v-app-bar>

    <v-navigation-drawer v-model="drawer" app temporary>
      <v-list-item>
        <v-list-item-content>
          <v-list-item-title
            >AMU IEEE Chapter
            <v-btn icon @click="changeMode">
              <v-icon>mdi-weather-sunny </v-icon>
            </v-btn></v-list-item-title
          >
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

    <v-main>
      <v-container>
        <nuxt />
      </v-container>
    </v-main>

    <spacer gap="3" />
    <Footer />
  </v-app>
</template>

<script>
import Footer from '@/components/Footer'
import Spacer from '@/components/Spacer'

export default {
  components: {
    Spacer,
    Footer,
  },
  data() {
    return {
      drawer: false,
      social: [
        { icon: 'mdi-facebook', link: 'https://facebook.com/AMUIEEE' },
        { icon: 'mdi-instagram', link: 'https://instagram.com/ieeeamu' },
      ],
      title: 'IEEE AMU',
      navItems: [
        { title: 'About', icon: 'mdi-home', link: '/#about-us' },
        { title: 'Team', icon: 'mdi-account', link: '/team' },
        { title: 'Blog', icon: 'mdi-book', link: '/blog' },
        { title: 'Contact Us', icon: 'mdi-contacts', link: '/contact' },
      ],
    }
  },
  methods: {
    changeMode() {
      if (this.$vuetify.theme.dark === true) {
        this.$vuetify.theme.dark = false
      } else {
        this.$vuetify.theme.dark = true
      }
    },
  },
}
</script>
<style scoped>
.developers {
  font-size: 10px;
}
</style>
