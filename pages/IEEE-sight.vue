<template>
  <div>
    <div>
      <v-container>
        <v-card class="mx-auto" max-width="1000">
          <v-img
            class="white--text align-end"
            height="200px"
            src="https://cdn.vuetifyjs.com/images/cards/docks.jpg"
          >
          </v-img>

          <v-card-text class="text--primary">
            <div text small>
              IEEE SIGHT AMU is a student affinity group whose mission is to
              help the local community through social actions and technical
              projects of a humanitarian and sustainable nature, always seeking
              to involve the local community in the projects so as to seek to
              understand a little the reality of this population and then be
              able to find effective and efficient solutions, obtaining mutual
              understanding and collaboration. Created in 2016, it had its
              official foundation before IEEE SIGHT ( Special Interest Group on
              Humanitarian Technology ) on December 18, 2018, one of the first
              IEEE SIGHT student affinity groups in Brazil. Our main objective
              is to put undergraduate students in contact with the population
              and their needs, as a way of using the knowledge that is passed on
              to us for a greater good. Our values are empathy, solidarity,
              teamwork, commitment and, of course, pride in being IEEE SIGHT.
              What we know and are can help in many different ways to make a
              better world, so we are always asking members: Shall we make a
              better world together?
            </div>
          </v-card-text>
        </v-card>
      </v-container>

      <v-row justify="center">
        <v-col cols="12" md="12">
          <div class="container">
            <div
              class="row team_cont"
              style="justify-content: center; background-color: #e3e1e1"
            >
              <v-col cols="12" sm="12">
                <v-card
                  class="mx-auto"
                  max-width="400"
                  color="rgba(74, 74, 74, 1)"
                >
                  <v-card-text class="text-center white--text headline">
                    Steering Committee
                  </v-card-text>
                </v-card>
              </v-col>

              <v-col
                v-for="members in sight_team"
                :key="members.id"
                cols="10"
                sm="6"
                md="3"
              >
                <v-card class="team-card our-team">
                  <v-img
                    id="pic"
                    class="center"
                    style="width: 100%, background-position: inherit"
                    :src="members.src"
                    lazy-src="https://www.aminz.org.nz/themes/portal/uploads/profile-default-large.jpg"
                  >
                  </v-img>
                  <v-card-text class="title text-center">
                    {{ members.name }}
                  </v-card-text>
                  <v-card-text class="title text-center">
                    {{ members.post }}
                  </v-card-text>
                </v-card>
              </v-col>
            </div>
          </div>
        </v-col>
      </v-row>
      <v-carousel hide-delimiters>
        <v-carousel-item
          v-for="(item, i) in items"
          :key="i"
          :src="item.src"
        ></v-carousel-item>
      </v-carousel>
    </div>
  </div>
</template>
<style scoped>
#pic {
  margin-top: 20px;
  border-radius: 100%;
  background-size: cover;
  height: 220px;
}
.center {
  display: block;
  margin-top: 1rem;
  margin-left: auto;
  margin-right: auto;
  width: 100%;
  height: 60%;
  width: 240px;
  border-radius: 100%;
  background-size: cover;
  height: 240px;
}
.team-card {
  margin: auto;
  height: 330px;
  background-color: rgba(0, 0, 0, 0.23);
  width: 380px;
  display: flex;
  justify-content: center;
  flex-direction: column;
}
.team_cont {
  margin-bottom: 1rem;
  border-radius: 10px;
  padding-bottom: 1.5rem;
}
</style>

<script>
export default {
  data() {
    return {
      sight_team: [],
      items: [
        {
          src: 'https://cdn.vuetifyjs.com/images/carousel/squirrel.jpg',
        },
        {
          src: 'https://cdn.vuetifyjs.com/images/carousel/sky.jpg',
        },
        {
          src: 'https://cdn.vuetifyjs.com/images/carousel/bird.jpg',
        },
        {
          src: 'https://cdn.vuetifyjs.com/images/carousel/planet.jpg',
        },
      ],
    }
  },
  created() {
    this.$fireStore
      .collection('sight_team')
      .get()
      .then((querySnapshot) => {
        querySnapshot.forEach((doc) => {
          const docObj = doc.data()
          docObj.id = doc.id
          this.sight_team.push(docObj)
        })
      })
  },
}
</script>
