<template>
  <v-app>
    <v-app-bar fixed app color="#072540" height="80">
      <v-app-bar-nav-icon
        class="hidden-md-and-up"
        @click.stop="drawer = !drawer"
      ></v-app-bar-nav-icon>

      <v-btn
        id="logo_container"
        :to="`/`"
        depressed
        height="50px"
        color="#072540"
      >
        <v-img class="main_logo" contain width="250px" height="50px"></v-img>
      </v-btn>

      <v-spacer />
      <div class="hidden-sm-and-down">
        <v-btn icon @click="changeMode">
          <v-icon color="white">mdi-weather-sunny </v-icon>
        </v-btn>
        <v-btn
          class="nav-link"
          active-class="active-link"
          text
          small
          to="/team"
        >
          <v-icon> mdi-account </v-icon>&nbsp; TEAM &nbsp;
        </v-btn>
        <v-btn
          class="nav-link"
          active-class="active-link"
          text
          small
          to="/events"
        >
          <v-icon> mdi-calendar </v-icon>&nbsp; EVENTS &nbsp;
        </v-btn>
        <v-btn
          class="nav-link"
          active-class="active-link"
          text
          small
          to="/blog"
        >
          <v-icon> mdi-book </v-icon>&nbsp; BLOG &nbsp;
        </v-btn>
        <v-menu open-on-hover bottom offset-y>
          <template v-slot:activator="{ on, attrs }">
            <v-btn
              class="nav-link"
              active-class="active-link"
              text
              small
              to="/home"
              v-bind="attrs"
              v-on="on"
            >
              <v-icon> mdi-leaf </v-icon>&nbsp; IEEE-SIGHT &nbsp;
            </v-btn>
          </template>
          <v-list color="#072540">
            <v-list-item
              v-for="(item, index) in items"
              :key="index"
              :to="item.link"
              link
            >
              <v-list-item-title style="color: #f4f4f4; font-size: 14px">{{
                item.title
              }}</v-list-item-title>
            </v-list-item>
          </v-list>
        </v-menu>
        <v-btn
          class="nav-link"
          active-class="active-link"
          text
          small
          to="/contact"
        >
          <v-icon> mdi-contacts </v-icon>&nbsp; CONTACT
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
        { title: 'IEEE-Sight', icon: 'mdi-leaf', link: '/home' },
        { title: 'Contact Us', icon: 'mdi-contacts', link: '/contact' },
      ],
      items: [
        { title: 'Home', link: '/home' },
        { title: 'Steering Committee', link: '/Steering Committee' },
        { title: 'Epochal', link: '/epochal' },
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
.nav-link::before {
  background-color: transparent;
}
.main_logo {
  background: url('https://firebasestorage.googleapis.com/v0/b/ieee-amu-7deee.appspot.com/o/Asset%202.png?alt=media&token=610204b4-0584-47f9-87bc-006e96c5271a');
  background-position: center;
  background-size: contain;
  background-repeat: no-repeat;
}
#logo_container {
  width: 300px;
}
@media screen and (max-width: 480px) {
  .main_logo {
    background: url('https://firebasestorage.googleapis.com/v0/b/ieee-amu-7deee.appspot.com/o/main_logo.png?alt=media&token=24eca515-027e-4c22-8634-205a3fb52fa5');
    background-position: center;
    background-size: contain;
    background-repeat: no-repeat;
  }
  #logo_container {
    width: 120px;
    left: 23%;
  }
}
.nav-link {
  color: white;
  display: inline-block;
  margin: 0;
  text-transform: uppercase;
}
.nav-link::after {
  display: block;
  content: '';
  border-bottom: solid 3px #019fb6;
  transform: scaleX(0);
  transition: transform 250ms ease-in-out;
}
.nav-link:hover:after {
  transform: scaleX(1);
}
.nav-link:hover {
  color: #019fb6 !important;
  transition: color 200ms ease-in;
}
.nav-link:after {
  transform-origin: 0% 50%;
  position: relative;
  top: 2px;
}
.active-link {
  /* border-bottom: solid 3px #019fb6; */
  color: #019fb6;
  font-weight: bold;
}
.developers {
  font-size: 10px;
}
</style>
