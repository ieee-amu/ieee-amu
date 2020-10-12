<template>
  <div>
    <div>
      <div class="d-flex flex-column justify-space-between align-center">
        <v-img
          contain
          src="https://firebasestorage.googleapis.com/v0/b/ieee-amu-7deee.appspot.com/o/IEEE%20Sight%20png.png?alt=media&token=79a11933-883d-432e-9ab6-e3bb59a825e6"
          width="800px"
          height="200px"
          style="margin-bottom: 1px"
        >
        </v-img>
        <v-chip
          class="ma-2"
          color="primary"
          style="
            font-family: 'Hammersmith One', sans-serif !important;
            font-size: 20px;
          "
        >
          Special Interest Group On Humanitarian Technology
        </v-chip>
      </div>
      <spacer gap="3" />
      <v-container>
        <v-card
          class="mx-auto"
          max-width="1000"
          color="#B2EBF2"
          style="font-family: 'Hammersmith One', sans-serif !important"
        >
          <v-card-text class="text--primary" style="">
            IEEE SIGHT AMU is a student affinity group whose mission is to help
            the local community through social actions and technical projects of
            a humanitarian and sustainable nature, always seeking to involve the
            local community in the projects so as to seek to understand a little
            the reality of this population and then be able to find effective
            and efficient solutions, obtaining mutual understanding and
            collaboration. Created in 2016, it had its official foundation
            before IEEE SIGHT ( Special Interest Group on Humanitarian
            Technology ) on December 18, 2018, one of the first IEEE SIGHT
            student affinity groups in India. Our main objective is to put
            undergraduate students in contact with the population and their
            needs, as a way of using the knowledge that is passed on to us for a
            greater good. Our values are empathy, solidarity, teamwork,
            commitment and, of course, pride in being IEEE SIGHT. What we know
            and are can help in many different ways to make a better world, so
            we are always asking members: Shall we make a better world together?
          </v-card-text>
        </v-card>
      </v-container>
      <spacer gap="3" />

      <v-card height="700">
        <v-tabs
          v-model="tab"
          height="100"
          background-color="primary"
          dark
          centered
        >
          <v-tab
            v-for="item in items1"
            :key="item.tab"
            style="
              font-family: 'Hammersmith One', sans-serif !important;
              font-size: 20px;
            "
          >
            {{ item.tab }}
          </v-tab>
        </v-tabs>

        <v-tabs-items v-model="tab">
          <v-tab-item v-for="item in items1" :key="item.tab">
            <v-card flat contain width="100%">
              <img
                id="sight_photo"
                contain
                class="center"
                width="60%"
                style="background-position: inherit"
                :src="item.src"
              />
              <img />
            </v-card>
            <v-card-text
              style="
                font-family: 'Hammersmith One', sans-serif !important;
                font-size: 18px;
              "
              >{{ item.content }}
            </v-card-text>
          </v-tab-item>
        </v-tabs-items>
      </v-card>

      <spacer gap="3" />

      <v-row justify="center">
        <v-col cols="12" md="12">
          <div class="container">
            <div
              class="row team_cont"
              style="justify-content: center; background-color: #b2ebf2"
            >
              <v-col cols="12" sm="12">
                <v-card class="mx-auto" max-width="400" color="primary">
                  <v-card-text
                    class="text-center white--text headline"
                    style="
                      font-family: 'Hammersmith One', sans-serif !important;
                    "
                  >
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
                  <v-card-text
                    class="title text-center"
                    style="padding-bottom: 0"
                  >
                    {{ members.name }}
                  </v-card-text>
                  <v-card-text class="title text-center" style="padding: 10px">
                    {{ members.post }}
                  </v-card-text>
                </v-card>
              </v-col>
            </div>
          </div>
        </v-col>
      </v-row>

      <v-row>
        <v-col cols="12" sm="12">
          <v-card-text class="text-center" style="margin: 3rem auto"
            ><h1
              style="
                font-family: 'Hammersmith One', sans-serif !important;
                text-decoration: underline;
              "
            >
              Get Involved
            </h1></v-card-text
          >
        </v-col>

        <v-col style="margin: 0 auto" cols="12" sm="8" md="4">
          <v-card class="mx-auto" max-width="400" height="200">
            <v-card-title
              style="
                color: midnightblue;
                font-family: 'Hammersmith One', sans-serif !important;
                font-size: 25px;
              "
              >Start a Group</v-card-title
            >

            <v-card-text
              class="text--primary"
              style="
                font-family: 'Hammersmith One', sans-serif !important;
                font-size: 15px;
              "
            >
              Have an idea which you would love to implement? Email us at
              amuieee.zhcet@gmail.com
            </v-card-text>
          </v-card>
        </v-col>
        <v-col style="margin: 0 auto" cols="12" sm="8" md="4">
          <v-card class="mx-auto" max-width="400" height="200">
            <v-card-title
              style="
                color: midnightblue;
                font-family: 'Hammersmith One', sans-serif !important;
                font-size: 25px;
              "
              >Join a Sight Group</v-card-title
            >

            <v-card-text
              class="text--primary"
              style="
                font-family: 'Hammersmith One', sans-serif !important;
                font-size: 15px;
              "
            >
              Join a desired project group and contribute? Email us at
              amuieee.zhcet@gmail.com 
            </v-card-text>
          </v-card>
        </v-col>
        <v-col style="margin: 0 auto" cols="12" sm="8" md="4">
          <v-card class="mx-auto" max-width="400" height="200">
            <v-card-title
              style="
                color: midnightblue;
                font-family: 'Hammersmith One', sans-serif !important;
                font-size: 25px;
              "
              >Volunteer</v-card-title
            >

            <v-card-text
              class="text--primary"
              style="
                font-family: 'Hammersmith One', sans-serif !important;
                font-size: 15px;
              "
            >
              Volunteer with us? Email us at amuieee.zhcet@gmail.com
            </v-card-text>
          </v-card>
        </v-col>
      </v-row>
    </div>
  </div>
</template>
<style scoped>
#sight_photo {
  margin-top: 1rem;

  
  width: 60%;

  /* border-radius: 100%; */
  background-size: cover;
  height: 450px;
  margin-bottom: 0.5rem;
}
#pic {
  margin-top: 20px;
  border-radius: 100%;
  background-size: cover;
  /* height: 220px; */
}
.center {
  display: block;
  margin-top: 1rem;
  margin-left: auto;
  margin-right: auto;
  width: 100%;
  height: 60%;
  width: 240px;
  /* border-radius: 100%; */
  background-size: cover;
  height: 240px;
}
.team-card {
  margin: auto;
  /* height: 330px; */
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
import Spacer from '@/components/Spacer'
export default {
  components: {
    Spacer,
  },
  data() {
    return {
      sight_team: [],
      tab: null,
      items1: [
        {
          tab: 'Vision',

          src:
            'https://firebasestorage.googleapis.com/v0/b/ieee-amu-7deee.appspot.com/o/sight-photos%2Fpoor-2754335.jpg?alt=media&token=a75cb7e6-fb16-4695-afd7-243455aa0300',

          content:
            'To help the local community through social actions and technical projects of a humanitarian and sustainable nature, always seeking to involve the local community in the projects so as to seek to understand a little the reality of this population and then be able to find effective and efficient solutions, obtaining mutual understanding and collaboration',
        },
        {
          tab: 'Mission',
          src:
            'https://firebasestorage.googleapis.com/v0/b/ieee-amu-7deee.appspot.com/o/sight-photos%2Ftechnology-4256272.jpg?alt=media&token=2f52ddbc-cec0-4bde-a723-7665b0d9c882',
          content:
            'Our main objective is to put undergraduate students in contact with the population and their needs, as a way of using the knowledge that is passed on to us for a greater good.',
        },
        {
          tab: 'Values',
          src:
            'https://firebasestorage.googleapis.com/v0/b/ieee-amu-7deee.appspot.com/o/sight-photos%2Fdoctor-870361_1920.jpg?alt=media&token=6dc6f072-a331-45d8-959e-460b6f8a2bac',
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

