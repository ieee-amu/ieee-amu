<template>
  <div>
    <div>
      <h2
        class="heading"
        align="center"
        style="margin-top: 20px; font-weight: bold; font-size: 50px"
      >
        Steering Commitee
      </h2>
      <v-container>
        <!-- -----------------------------------------------
            Start Form Banner1
        ----------------------------------------------- -->
        <v-row v-for="members in sight_team" :key="members.id" justify="center">
          <v-col cols="12" md="7" lg="5" class="d-flex align-center">
            <div class="block text-center text-md-left">
              <h2 class="formbanner1-title font-weight-bold">
                {{ members.name }}
              </h2>
              <p class="mt-2 pt-2" style="font-weight: bold">
                {{ members.post }}
              </p>
              <p class="mt-2 pt-2" style="text-align: justify">
                {{ members.description }}
              </p>
            </div>
          </v-col>
          <v-col cols="12" md="5" lg="6" class="ml-auto">
            <v-img
              id="pic"
              class="center"
              background-position:
              inherit
              max-height="250"
              max-width="250"
              :src="members.src"
              alt="banner"
            />
          </v-col>
        </v-row>

        <!-- -----------------------------------------------
            End Form Banner1
        ----------------------------------------------- -->
      </v-container>
    </div>
  </div>
</template>
<style scoped>
@media (max-width: 600px) {
  #sight_photo {
    width: 100% !important;
  }
  .team_cont {
    margin-top: 5rem !important;
  }
  #heading {
    margin: -1rem;
  }
}
@media (max-width: 100px) {
  #heading {
    margin-bottom: -2rem;
  }
}
.block {
  margin-left: 0px;
  margin-right: -250px;
}
.image {
  width: 100%;
}
.formbanner1-title {
  font-size: 35px;
  line-height: 1;
  letter-spacing: -1px;
}
.sidebar {
  position: relative;
  margin-left: -350px;
  align-items: left;
  height: 120%;
  opacity: 0.5;
}
.page {
  background-size: cover;
  background-position: center center;
  background-repeat: no-repeat;
  background-image: url(http://dslv9ilpbe7p1.cloudfront.net/u629X8KbX0CDXYWcoCRJlw_store_banner_image.jpeg);
}
.back {
  background-size: cover;
  background-position: center center;
  background-repeat: no-repeat;
  width: 100%;
  background-blend-mode: hard-light;
  height: 53vh;
  opacity: 0.85;
  position: absolute;
}
#sight_photo {
  margin-top: 1rem;
  background-position: inherit;
  width: 60%;
  /* border-radius: 100%; */
  background-size: cover;
  height: 450px;
  margin-bottom: 0.5rem;
}
#pic {
  margin-top: 40px;
  border-radius: 100%;
  background-size: cover;
  /* height: 220px; */
}
.nav {
  margin-top: 0.5cm;
  width: 200%;
  background: #ff416c; /* fallback for old browsers */
  background: -webkit-linear-gradient(
    to right,
    #ff4b2b,
    #ff416c
  ); /* Chrome 10-25, Safari 5.1-6 */
  background: linear-gradient(
    to right,
    #ff4b2b,
    #ff416c
  ); /* W3C, IE 10+/ Edge, Firefox 16+, Chrome 26+, Opera 12+, Safari 7+ */
  /* W3C, IE 10+/ Edge, Firefox 16+, Chrome 26+, Opera 12+, Safari 7+ */

  /* W3C, IE 10+/ Edge, Firefox 16+, Chrome 26+, Opera 12+, Safari 7+ */
}
.center {
  display: block;
  margin-top: 5rem;
  margin-left: 250px;
  margin-right: 0;
  width: 100%;
  height: 60%;
  width: 240px;
  /* border-radius: 100%; */
  background-size: cover;
  height: 240px;
}
.team-card {
  margin-top: 2rem;
  /* height: 330px; */
  background-color: rgba(0, 0, 0, 0.23);
  width: 440px;
  display: flex;
  justify-content: center;
  flex-direction: column;
}
.team_cont {
  margin-bottom: 1rem;
  border-radius: 10px;
  padding-bottom: 1.5rem;
}
@media (max-width: 700px) {
  .carosel .v-carousel {
    height: auto !important;
  }
  .carosel .v-carousel__item {
    height: auto !important;
  }
  .carosel .v-image__image {
    background-size: contain !important;
  }
}
</style>
<script>
export default {
  components: {},
  data() {
    return {
      sight_team: [],
      tab: null,
      items1: [
        {
          tab: 'Vision',
          content:
            'To help the local community through social actions and technical projects of a humanitarian and sustainable nature, always seeking to involve the local community in the projects so as to seek to understand a little the reality of this population and then be able to find effective and efficient solutions, obtaining mutual understanding and collaboration',
        },
        {
          tab: 'Mission',
          content:
            'Our main objective is to put undergraduate students in contact with the population and their needs, as a way of using the knowledge that is passed on to us for a greater good.',
        },
        {
          tab: 'Values',
          content:
            'Our values are empathy, solidarity, teamwork, commitment and, of course, pride in being IEEE SIGHT.',
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
