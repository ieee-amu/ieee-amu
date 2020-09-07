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
    <spacer gap="3" />
    <v-container>
      <v-row justify="space-between">
        <v-col v-for="team in teams" :key="team.title" cols="auto">
          <v-card>
            <v-img
              :src="team.src"
              class="white--text align-end"
              gradient="to bottom, rgba(0,0,0,.1), rgba(0,0,0,.5)"
              height="310px"
              max-width="310px"
              position="center"
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
              <v-card-title v-text="team.title"></v-card-title>
            </v-img>
            <v-card-text class="blockquote" v-text="team.text"></v-card-text>
            <v-col class="lighten-3 text-center pa-0">
              <v-btn
                v-for="(link, type) in team.links"
                :key="type"
                :color="iconColor(type)"
                class="mx-3 my-2"
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
