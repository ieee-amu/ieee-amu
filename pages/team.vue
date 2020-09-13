<template>
  <v-container>
    <v-row justify="center">
      <v-col cols="10" sm="6">
        <v-card color="rgba(182, 187, 165, 1)">
          <v-card-text class="text-center headline black--text">
            TEAM MEMBERS
          </v-card-text>
        </v-card>
      </v-col>
    </v-row>
    <spacer gap="2" />
    <v-container justify="center space-between">
      <v-row>
        <v-col
          v-for="team in teams"
          :key="team.title"
          :style="{ order: team.order }"
          cols="12"
          md="6"
        >
          <v-card class="team-card">
            <v-img
              class="center"
              style="width: 100%, background-position: inherit"
              :src="team.src"
              gradient="to bottom, rgba(0,0,0,.1), rgba(0,0,0,.5)"
              lazy-src="https://www.aminz.org.nz/themes/portal/uploads/profile-default-large.jpg"
            >
              <template v-slot:placeholder>
                <v-row class="fill-height ma-0" align="center" justify="center">
                  <v-progress-circular
                    indeterminate
                    color="grey lighten-5"
                  ></v-progress-circular>
                </v-row>
              </template>
            </v-img>
            <v-card-text class="title text-center">
              {{ team.title }}
            </v-card-text>
            <v-card-text class="blockquote text-center">{{
              team.text
            }}</v-card-text>
            <v-col class="lighten-3 text-center pa-0">
              <v-btn
                v-for="(link, type) in team.links"
                :key="type"
                :color="iconColor(type)"
                class="mx-2 my-2"
                fab
                dark
                small
              >
                <a
                  :href="getLink(link, type)"
                  target="_blank"
                  rel="noopener"
                  style="text-decoration: none; color: inherit"
                >
                  <v-icon dark size="18">{{ icon(type) }}</v-icon>
                </a>
              </v-btn>
            </v-col>
          </v-card>
        </v-col>
      </v-row>
    </v-container>
  </v-container>
</template>
<script>
import Spacer from '@/components/Spacer'

export default {
  components: {
    Spacer,
  },
  data() {
    return {
      teams: [],
    }
  },
  created() {
    this.$fireStore
      .collection('teams')
      .get()
      .then((querySnapshot) => {
        querySnapshot.forEach((doc) => {
          const docObj = doc.data()
          docObj.id = doc.id
          this.teams.push(docObj)
        })
      })
  },
  methods: {
    iconColor(type) {
      switch (type) {
        case 'facebook':
          return 'blue darken-4'
        case 'email':
          return 'red darken-1'
        case 'g-plus':
          return 'red darken-4'
        case 'linkedin':
          return 'indigo darken-1'
        case 'mobile':
          return 'green darken-3'
        case 'twitter':
          return 'light-blue darken-1'
        case 'github':
          return 'black'
      }
    },
    icon(type) {
      switch (type) {
        case 'g-plus':
          return 'mdi-google-plus'
        case 'mobile':
          return 'mdi-phone'
        default:
          return `mdi-${type}`
      }
    },
    getLink(link, type) {
      if (type === 'email') {
        return 'mailto:' + link
      } else if (type === 'mobile') {
        return 'tel:' + link
      } else if (!link.startsWith('http://') && !link.startsWith('https://')) {
        return '//' + link
      }
      return link
    },
  },
}
</script>
<style scoped>
.center {
  display: block;
  margin-left: auto;
  margin-right: auto;
  width: 85%;
  height: 65%;
}
.team-card {
  margin: auto;
  height: 500px;
  width: 340px;
}
.v-card__subtitle,
.v-card__text,
.v-card__title {
  padding: 12px;
}
@media (max-width: 480px) {
  .v-card__subtitle,
  .v-card__text,
  .v-card__title {
    padding: 6px;
  }
  .blockquote {
    padding: 6px;
  }
}
</style>
