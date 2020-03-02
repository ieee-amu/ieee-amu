<template>
  <div>
    <v-carousel>
      <v-carousel-item v-for="(item, i) in items" :key="i" :src="item.src" />
    </v-carousel>
    <v-container>
      <v-layout row wrap>
        <v-flex sm12 lg8>
          <v-layout row wrap>
            <v-flex xs12 sm6>
              <v-card class="mt-3 mr-3">
                <v-card-title primary-title>
                  <div>
                    <h3 class="headline mb-0">
                      About SSGSA
                    </h3>
                  </div>
                </v-card-title>
                <v-card-title primary-title>
                  <div class="card-text">
                    The Sir Syed Global Scholar Award (SSGSA), formerly known as
                    the Sir Syed Excellence in Science Award (SSESA), is a
                    merit-based scholarship that is awarded to academically
                    outstanding students at Master's level from all faculties,
                    including sciences, life sciences, medicine, arts, business,
                    commerce, law, and education at the Aligarh Muslim
                    University. All donations and contributions directly sponsor
                    the attempts of talented students to secure admission in PhD
                    programs at centers of international repute. The Sir Syed
                    Education Society of North America, a 501 © (3) non-profit
                    organization, annually administers the Sir Syed Global
                    Scholar Award (SSGSA).
                  </div>
                </v-card-title>
                <v-card-actions>
                  <nuxt-link to="/about" style="text-decoration: none">
                    <v-btn flat color="orange">
                      KNOW MORE
                    </v-btn>
                  </nuxt-link>
                </v-card-actions>
              </v-card>
            </v-flex>
            <v-flex xs12 sm6>
              <v-card class="mt-3">
                <v-card-title primary-title>
                  <div>
                    <h3 class="headline mb-0">
                      Testimonials
                    </h3>
                  </div>
                </v-card-title>
                <v-card-title primary-title>
                  <div class="card-text">
                    Being a SSGSA awardee and a proud member of the family, I
                    feel very much privileged. SSGSA not only made me dream big
                    but also helped me to attain success. I am really amazed to
                    observe the working style of this family and the extent to
                    which they cooperate with the students.
                    <br />
                    The struggles of these seniors from the Aligarh fraternity
                    were a great source of inspiration to me and as a result of
                    this motivation, I got selected for an internship at
                    European Organization for Nuclear Research (CERN), Geneva,
                    Switzerland which, I believe, is the best thing to have
                    happened to me so far. CERN is not only the world's largest
                    Physics laboratory but also one of the most prestigious
                    research institutes of the world.
                    <br />
                    Had I not got the SSGSA award, I probably wouldn't have got
                    the motivation to apply there (in CERN) too. So, all credit
                    goes to SSGSA, which changed my perceptions, dreams and
                    motivations of life.
                  </div>
                </v-card-title>
                <v-card-actions>
                  <nuxt-link to="/testimonials" style="text-decoration: none">
                    <v-btn flat color="orange">
                      KNOW MORE
                    </v-btn>
                  </nuxt-link>
                </v-card-actions>
              </v-card>
            </v-flex>
          </v-layout>
        </v-flex>
        <v-flex sm12 lg4>
          <v-card
            v-for="link in links"
            :key="link[1]"
            class="mb-3 ml-3 mt-3"
            color="accent"
            router
            exact
          >
            <a
              :href="link[1]"
              target="_blank"
              style="text-decoration: none; color: inherit"
            >
              <v-container>
                <v-layout row wrap>
                  <v-flex xs12>
                    {{ link[0] }}
                  </v-flex>
                </v-layout>
              </v-container>
            </a>
          </v-card>
          <v-card color="accent" class="mb-3 mt-3 ml-3">
            <v-container>
              <v-layout row wrap>
                <v-flex xs12 class="text-xs-center">
                  <v-icon x-large color="success">
                    notifications_active
                  </v-icon>
                </v-flex>
              </v-layout>
            </v-container>
          </v-card>
          <v-card
            v-for="update in updates"
            :key="update[1]"
            class="mb-3 mt-3 ml-3"
            color="accent"
            router
            exact
          >
            <a
              :href="update[1]"
              target="_blank"
              style="text-decoration: none; color: inherit"
            >
              <v-container>
                <v-layout row wrap>
                  <v-flex xs12>
                    {{ update[0] }}
                  </v-flex>
                </v-layout>
              </v-container>
            </a>
          </v-card>
        </v-flex>
      </v-layout>
    </v-container>
  </div>
</template>

<script>
export default {
  data() {
    return {
      links: [
        [
          'SSGSA 2019 results are declared - click here to see',
          'http://ssgsa.us/assets/SSGSA_Awardees_2019-20.pdf'
        ],
        [
          'Press release statement on SSGSA 2019 results',
          'http://ssgsa.us/assets/SSGSA_results_2019_Press_release_statement.pdf'
        ],
        ['What is SSGSA', '/about']
      ],
      updates: [
        [
          'AMU students complete summer internships at US labs',
          'http://www.amu.ac.in/about3.jsp?did=7568'
        ],
        [
          'SSGSA signs MoU with AMU for the Summer Internship Program: International Summer Research Award (ISRA)',
          'http://www.business-standard.com/article/news-ians/now-amu-students-to-do-summer-internships-in-us-113080300900_1.html'
        ]
      ],
      items: [
        {
          src: 'https://cdn.vuetifyjs.com/images/carousel/squirrel.jpg'
        },
        {
          src: 'https://cdn.vuetifyjs.com/images/carousel/sky.jpg'
        },
        {
          src: 'https://cdn.vuetifyjs.com/images/carousel/bird.jpg'
        },
        {
          src: 'https://cdn.vuetifyjs.com/images/carousel/planet.jpg'
        }
      ]
    }
  }
}
</script>
