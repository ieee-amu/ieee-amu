<template>
  <v-app>
    <v-app-bar fixed app color="#03254c">
      <v-app-bar-nav-icon
        class="hidden-md-and-up"
        @click.stop="drawer = !drawer"
      ></v-app-bar-nav-icon>
      <v-btn
        style="background-color: #1167b1; border-radius: 5px"
        :to="`/`"
        depressed
        width="250px"
        height="50px"
      >
        <v-img
          src="https://firebasestorage.googleapis.com/v0/b/ieee-amu.appspot.com/o/logo.svg?alt=media&token=4f818ffd-d53e-463b-ada8-78b568e323cd"
          width="250px"
          height="50px"
        ></v-img>
      </v-btn>
      <v-spacer />
      <div class="hidden-sm-and-down">
        <v-btn color="white" icon @click="changeMode">
          <v-icon>mdi-weather-sunny </v-icon>
        </v-btn>
        <v-btn
          color="white"
          class="nav-link"
          active-class="active-link"
          text
          small
          to="/team"
        >
          <v-icon color="white"> mdi-account </v-icon>&nbsp; TEAM &nbsp;
        </v-btn>
        <v-btn
          color="white"
          class="nav-link"
          active-class="active-link"
          text
          small
          to="/events"
        >
          <v-icon color="white"> mdi-calendar </v-icon>&nbsp; EVENTS &nbsp;
        </v-btn>
        <v-btn
          color="white"
          class="nav-link"
          active-class="active-link"
          text
          small
          to="/blog"
        >
          <v-icon color="white"> mdi-book </v-icon>&nbsp; BLOG &nbsp;
        </v-btn>
        <v-btn
          color="white"
          class="nav-link"
          active-class="active-link"
          text
          small
          to="/sight"
        >
          <v-icon color="white"> mdi-leaf </v-icon>&nbsp; IEEE-SIGHT &nbsp;
        </v-btn>
        <v-btn
          color="white"
          class="nav-link"
          active-class="active-link"
          text
          small
          to="/contact"
        >
          <v-icon color="white"> mdi-contacts </v-icon>&nbsp; CONTACT
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
        { title: 'Team', icon: 'mdi-account', link: '/team' },
        { title: 'Events', icon: 'mdi-calendar', link: '/events' },
        { title: 'Blog', icon: 'mdi-book', link: '/blog' },
        { title: 'IEEE-Sight', icon: 'mdi-leaf', link: '/sight' },
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
.theme--light.v-application {
  background-color: var(--v-background-base, #d0efff) !important;
}
.nav-link::before {
  background-color: transparent;
}
.nav-link {
  padding: 1rem !important;
  border-bottom: 4px solid transparent;

  border-radius: 0;
  text-decoration: none;
  transition: all 0.2s;
}
.nav-link::after {
  content: '';
  display: block;
  position: absolute;
  left: 0;
  top: 32px;
  width: 100%;
  height: 4px;
  background-color: white;
  animation: slide-out 500ms ease-in-out forwards;
}
.nav-link:hover {
  color: white;
}
.nav-link:hover::after {
  animation: slide-in 300ms;
}
@keyframes slide-out {
  0% {
    transform: none;
  }
  100% {
    transform: translate(1000%, 0);
  }
}
@keyframes slide-in {
  0% {
    transform: translate(-100%, 0);
  }
  100% {
    transform: none;
  }
}
.active-link {
  color: white;
  border-bottom: 4px solid white;
}
.developers {
  font-size: 10px;
}
</style>
