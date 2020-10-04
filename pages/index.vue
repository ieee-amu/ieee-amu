<template>
  <div>
    <v-carousel id="carousel" cycle>
      <v-carousel-item v-for="(item, i) in items" :key="i" :src="item.src" />
    </v-carousel>
    <div id="mobile_header">
      <v-img
        src="https://firebasestorage.googleapis.com/v0/b/ieee-amu-7deee.appspot.com/o/Logopit_1591939004987%201%402x.png?alt=media&token=ab8d9a74-757d-4171-ad17-b030a36fd48a"
      ></v-img>
    </div>
    <spacer gap="5" />
    <v-divider />
    <spacer gap="5" />
    <v-container>
      <v-card id="about-us" class="mb-3" elevation="10">
        <v-row justify="center">
          <p
            id="about-us-1"
            class="display-2"
            style="font-family: 'Hammersmith One', sans-serif !important"
          >
            About Us
          </p>
        </v-row>
        <v-main style="padding: 0" class="card-text">
          <p id="about-us-2" class="blockquote">
            Welcome to IEEE-AMU, a community of erudite and professional
            individuals, whose purpose is to disseminate knowledge on technical
            work, seminars, conferences and accreditations while advocating
            benefits to it's members. Being the world's largest technical
            professional society, IEEE's benefits include venues and tools for
            members to network, and build valuable professional connections and
            leadership skills.
            <br />
            <br />
            Thank you for stopping by.
          </p>
        </v-main>
      </v-card>
      <spacer gap="5" />
      <v-row dense>
        <v-img
          contain
          src="https://firebasestorage.googleapis.com/v0/b/ieee-amu.appspot.com/o/amu-logo.png?alt=media&token=fe5c2453-4526-4934-8679-0ca61b0883f8"
          width="250px"
          height="250px"
        >
        </v-img>

        <v-img
          contain
          src="https://firebasestorage.googleapis.com/v0/b/ieee-amu.appspot.com/o/ieee-logo.png?alt=media&token=3b7d2df4-15b8-4b65-b148-72b0249f5cb8"
          width="250px"
          height="250px"
        >
        </v-img>
      </v-row>
      <spacer gap="5" />
    </v-container>

    <v-container>
      <v-row justify="center">
        <v-col cols="12" md="12">
          <div class="container">
            <div
              class="row team_cont"
              style="justify-content: center; background-color: #e3e1e1"
            >
              <v-col cols="12" sm="12">
                <v-card color="rgba(74, 74, 74, 1)">
                  <v-card-text
                    class="text-center white--text headline"
                    style="
                      font-family: 'Hammersmith One', sans-serif !important;
                    "
                  >
                    Team-Coordinators
                  </v-card-text>
                </v-card>
              </v-col>

              <v-col
                v-for="coordinator in coordinators"
                :key="coordinator.id"
                cols="10"
                sm="6"
                md="3"
              >
                <v-card class="team-card our-team">
                  <v-img
                    id="pic"
                    class="center"
                    style="width: 100%, background-position: inherit"
                    :src="coordinator.src"
                    lazy-src="https://www.aminz.org.nz/themes/portal/uploads/profile-default-large.jpg"
                  >
                  </v-img>
                  <v-card-text class="title text-center">
                    {{ coordinator.name }}
                  </v-card-text>
                </v-card>
              </v-col>
              <v-btn href="/team" class="btn">
                <a> View Team &nbsp;<v-icon>mdi-arrow-right-bold</v-icon></a>
              </v-btn>
            </div>
          </div>
        </v-col>
      </v-row>
      <v-row>
        <v-col cols="12" sm="12">
          <v-card-text class="text-center" style="margin: 3rem auto"
            ><h1 style="font-family: 'Hammersmith One', sans-serif !important">
              Recent News
            </h1></v-card-text
          >
        </v-col>

        <v-col style="margin: 0 auto" cols="12" sm="8" md="4">
          <v-card class="mx-auto" max-width="400">
            <v-img
              class="white--text align-end"
              height="200px"
              src="https://www.greenbiz.com/sites/default/files/styles/gbz_article_primary_breakpoints_kalapicture_screen-lg_1x/public/images/articles/featured/partnership_0.jpg?itok=ZekH-so_&timestamp=1445488550"
            >
              <v-card-title
                style="
                  color: midnightblue;
                  font-family: 'Hammersmith One', sans-serif !important;
                "
                >WASTE HEAT MANAGEMENT AND ELECTRICITY
                GENERATATION</v-card-title
              >
            </v-img>

            <v-card-text class="text--primary">
              IEEE SIGHT student’s chapter (AMU) organised an informative
              session for the students of Women’s polytechnic, Aligarh Muslim
              University to spread awareness about the utilisation of
              technologies for Humanitarian causes and sustainable development.
              A lecture was delivered by Pakhil Singh, IEEE SIGHT Student
              Coordinator on “Waste Heat Management and Electricity Generation”.
              In this lecture, the utilisation and recovery of waste heat from
              exhausts of vehicles, outdoor units of Air conditioners, Power
              Plants, Refineries, heat wasted in aeroplane drag and their
              effective conversion into Electricity was discussed.
            </v-card-text>

            <v-card-actions>
              <v-btn
                color="orange"
                href="https://drive.google.com/file/d/1OTsY4bfp0mvKBVOdkDrekGO-n0L91GF4/view?usp=sharing"
                target="_blank"
                rel="noopener"
                text
              >
                Read More
              </v-btn>

              <v-btn color="orange" to="./blog" text> Explore </v-btn>
            </v-card-actions>
          </v-card>
        </v-col>
        <v-col style="margin: 0 auto; height: auto" cols="12" sm="8" md="4">
          <v-card>
            <instagram-embed
              class="insta"
              :url="'https://www.instagram.com/p/CE6Nls1gPbf/?igshid=u6liozf0coet'"
            />
          </v-card>
        </v-col>
        <v-col style="margin: 0 auto" cols="12" sm="8" md="4">
          <v-card class="mx-auto">
            <iframe
              class="feed"
              src="https://www.facebook.com/plugins/page.php?href=https%3A%2F%2Fwww.facebook.com%2FAMUIEEE%2F&tabs=timeline&width=340&height=500&small_header=false&adapt_container_width=true&hide_cover=false&show_facepile=true&appId"
              height="500"
              width="250"
              style="border: none; overflow: hidden; width: fit-content"
              scrolling="no"
              frameborder="0"
              allowTransparency="true"
              allow="encrypted-media"
            ></iframe>
          </v-card>
        </v-col>
      </v-row>
      <v-row>
        <v-card-text class="text-center" style="margin: 3rem auto"
          ><h1 style="font-family: 'Hammersmith One', sans-serif !important">
            Contact Us
          </h1></v-card-text
        >
        <v-col class="contact" cols="8" md="4"
          ><v-icon style="color: black" size="50">mdi-cellphone-iphone</v-icon>
          <h3 style="padding: 1rem 0">Phone</h3>
          <v-card-subtitle
            ><a
              style="text-decoration: none; color: inherit"
              href="tel:+919412690509"
              >+91-9412690509</a
            ></v-card-subtitle
          ></v-col
        >
        <v-col class="contact" cols="8" md="4"
          ><v-icon style="color: black" size="50">mdi-email</v-icon>
          <h3 style="padding: 1rem 0">Email</h3>
          <v-card-subtitle
            ><a
              href="mailto:ieeeamu.zhcet@gmail.com"
              style="text-decoration: none; color: inherit"
              >ieeeamu.zhcet@gmail.com</a
            ></v-card-subtitle
          ></v-col
        ><v-col class="contact" cols="8" md="4">
          <v-icon style="color: black" size="50">mdi-google-maps</v-icon>
          <h3 style="padding: 1rem 0">Address</h3>
          <v-card-subtitle class="text-center">
            Electrical Engineering Department ZHCET, Uttar Pradesh 202002
          </v-card-subtitle>
        </v-col>
      </v-row>
      <v-row
        ><v-col cols="12">
          <v-card>
            <iframe
              src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d3525.5822502153687!2d78.07415941490626!3d27.914790282706377!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x3974a4fcb0ea6ddb%3A0x765b62941f223b8e!2sZakir%20Husain%20College%20of%20Engineering%20and%20Technology%2C%20AMU!5e0!3m2!1sen!2sin!4v1600017095357!5m2!1sen!2sin"
              frameborder="0"
              style="border: 0"
              width="100%"
              height="200px"
              allowfullscreen=""
              aria-hidden="false"
              tabindex="0"
            ></iframe> </v-card></v-col
      ></v-row>
    </v-container>
  </div>
</template>

<script>
import Spacer from '@/components/Spacer'
import InstagramEmbed from 'vue-instagram-embed'
export default {
  components: {
    Spacer,
    InstagramEmbed,
  },
  data() {
    return {
      coordinators: [],
      items: [
        {
          src:
            'https://firebasestorage.googleapis.com/v0/b/ieee-amu-7deee.appspot.com/o/Logopit_1591939004987%201%402x.png?alt=media&token=ab8d9a74-757d-4171-ad17-b030a36fd48a',
        },

        {
          src:
            'https://firebasestorage.googleapis.com/v0/b/ieee-amu.appspot.com/o/carousel4.jpeg?alt=media&token=f0d73c2d-4705-4f0f-9645-d1feec377869',
        },
        {
          src:
            'https://firebasestorage.googleapis.com/v0/b/ieee-amu-7deee.appspot.com/o/IMG_20191108_122555_50_1_58.jpg?alt=media&token=e0f748c5-0643-4109-8981-ebbbd77934d1',
        },
        {
          src:
            'https://firebasestorage.googleapis.com/v0/b/ieee-amu-7deee.appspot.com/o/IMG_20191110_140243_1_60_1_58_1_64.jpg?alt=media&token=a48305cd-31f0-4b76-a4d6-6604668ce9b7',
        },
      ],
    }
  },
  created() {
    this.$fireStore
      .collection('coordinators')
      .get()
      .then((querySnapshot) => {
        querySnapshot.forEach((doc) => {
          const docObj = doc.data()
          docObj.id = doc.id
          this.coordinators.push(docObj)
        })
      })
  },
}
</script>
<style scoped>
@media (max-width: 700px) {
  #carousel {
    display: none;
  }
  #mobile_header {
    display: block !important;
  }
}
#mobile_header {
  display: none;
}
#about-us-1 {
  padding-top: 15px;
}
.insta {
  margin: auto;
  width: fit-content;
  height: fit-content;
}
#about-us-2 {
  text-align: justify;
  margin-left: 20px;
  margin-right: 20px;
  padding: 10px;
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
#pic {
  margin-top: 10px;
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
.btn {
  margin-top: 20px;
  color: royalblue;
  background: white;
  border: white 2px solid;
  padding: 10px;
  transition: all 0.2s;
}
.btn a {
  text-decoration: none;
}
.team_cont {
  margin-bottom: 1rem;
  border-radius: 10px;
  padding-bottom: 1.5rem;
}

.btn:hover {
  color: white;
  background: royalblue;
  border: royalblue 2px solid;
}
.contact,
.feed {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  margin: auto;
}
</style>
