<template>
  <div>
    <v-carousel cycle>
      <v-carousel-item v-for="(item, i) in items" :key="i" :src="item.src" />
    </v-carousel>
    <spacer gap="5" />
    <v-divider />
    <spacer gap="5" />
    <v-container>
      <v-card id="about-us" class="mb-3" elevation="10">
        <v-row justify="center">
          <p id="about-us-1" class="display-2">About Us</p>
        </v-row>
        <v-main class="card-text">
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
                  <v-card-text class="text-center white--text headline">
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
          <v-card flat>
            <v-card-text class="text-center headline">
              Recent News
            </v-card-text>
          </v-card>
        </v-col>
        <v-col style="margin: auto" cols="12" sm="8" md="4">
          <v-card class="mx-auto" outlined>
            <v-title class="headline mb-1"
              >WASTE HEAT MANAGEMENT AND ELECTRICITY GENERATATION</v-title
            >
            <spacer />

            <v-text>
              IEEE SIGHT student’s chapter (AMU) organised an informative
              session for the students of Women’s polytechnic, Aligarh Muslim
              University to spread awareness about the utilisation of
              technologies for Humanitarian causes and sustainable development.
              A lecture was delivered by Pakhil Singh, IEEE SIGHT Student
              Coordinator on “Waste Heat Management and Electricity Generation”.
            </v-text>
            <spacer />
            <v-btn class="btn" to="./blog"
              ><a
                >Read More Newsletters &nbsp;<v-icon
                  >mdi-arrow-right-bold</v-icon
                ></a
              ></v-btn
            >
          </v-card>
        </v-col>
        <v-col style="margin: auto" cols="12" sm="8" md="4">
          <v-card class="mx-auto" outlined>
            <v-title class="headline mb-1">facebook</v-title>
            <spacer />

            <v-text>
              IEEE SIGHT student’s chapter (AMU) organised an informative
              session for the students of Women’s polytechnic, Aligarh Muslim
              University to spread awareness about the utilisation of
              technologies for Humanitarian causes and sustainable development.
              A lecture was delivered by Pakhil Singh, IEEE SIGHT Student
              Coordinator on “Waste Heat Management and Electricity Generation”.
            </v-text>
            <spacer />
            <v-btn class="btn" to="./blog"
              ><a
                >Read More Newsletters &nbsp;<v-icon
                  >mdi-arrow-right-bold</v-icon
                ></a
              ></v-btn
            >
          </v-card>
        </v-col>
        <v-col style="margin: auto; height: auto" cols="12" sm="8" md="4">
          <v-card style="display: flex; justify-content: center">
            <blockquote
              class="instagram-media"
              data-instgrm-captioned
              data-instgrm-permalink="https://www.instagram.com/p/CE6Nls1gPbf/?utm_source=ig_embed&amp;utm_campaign=loading"
              data-instgrm-version="12"
              style="
                background: #fff;
                border: 0;
                border-radius: 3px;
                box-shadow: 0 0 1px 0 rgba(0, 0, 0, 0.5),
                  0 1px 10px 0 rgba(0, 0, 0, 0.15);
                margin: 1px;
                min-width: 326px;
                padding: 0;
                width: 99.375%;
                width: -webkit-calc(100% - 2px);
                width: calc(100% - 2px);
              "
            >
              <div style="padding: 16px">
                <a
                  href="https://www.instagram.com/p/CE6Nls1gPbf/?utm_source=ig_embed&amp;utm_campaign=loading"
                  style="
                    background: #ffffff;
                    line-height: 0;
                    padding: 0 0;
                    text-align: center;
                    text-decoration: none;
                    width: 100%;
                  "
                  target="_blank"
                >
                  <div
                    style="
                      display: flex;
                      flex-direction: row;
                      align-items: center;
                    "
                  >
                    <div
                      style="
                        background-color: #f4f4f4;
                        border-radius: 50%;
                        flex-grow: 0;
                        height: 40px;
                        margin-right: 14px;
                        width: 40px;
                      "
                    ></div>
                    <div
                      style="
                        display: flex;
                        flex-direction: column;
                        flex-grow: 1;
                        justify-content: center;
                      "
                    >
                      <div
                        style="
                          background-color: #f4f4f4;
                          border-radius: 4px;
                          flex-grow: 0;
                          height: 14px;
                          margin-bottom: 6px;
                          width: 100px;
                        "
                      ></div>
                      <div
                        style="
                          background-color: #f4f4f4;
                          border-radius: 4px;
                          flex-grow: 0;
                          height: 14px;
                          width: 60px;
                        "
                      ></div>
                    </div>
                  </div>
                  <div style="padding: 19% 0"></div>
                  <div
                    style="
                      display: block;
                      height: 50px;
                      margin: 0 auto 12px;
                      width: 50px;
                    "
                  >
                    <svg
                      width="50px"
                      height="50px"
                      viewBox="0 0 60 60"
                      version="1.1"
                    >
                      <g
                        stroke="none"
                        stroke-width="1"
                        fill="none"
                        fill-rule="evenodd"
                      >
                        <g
                          transform="translate(-511.000000, -20.000000)"
                          fill="#000000"
                        >
                          <g>
                            <path
                              d="M556.869,30.41 C554.814,30.41 553.148,32.076 553.148,34.131 C553.148,36.186 554.814,37.852 556.869,37.852 C558.924,37.852 560.59,36.186 560.59,34.131 C560.59,32.076 558.924,30.41 556.869,30.41 M541,60.657 C535.114,60.657 530.342,55.887 530.342,50 C530.342,44.114 535.114,39.342 541,39.342 C546.887,39.342 551.658,44.114 551.658,50 C551.658,55.887 546.887,60.657 541,60.657 M541,33.886 C532.1,33.886 524.886,41.1 524.886,50 C524.886,58.899 532.1,66.113 541,66.113 C549.9,66.113 557.115,58.899 557.115,50 C557.115,41.1 549.9,33.886 541,33.886 M565.378,62.101 C565.244,65.022 564.756,66.606 564.346,67.663 C563.803,69.06 563.154,70.057 562.106,71.106 C561.058,72.155 560.06,72.803 558.662,73.347 C557.607,73.757 556.021,74.244 553.102,74.378 C549.944,74.521 548.997,74.552 541,74.552 C533.003,74.552 532.056,74.521 528.898,74.378 C525.979,74.244 524.393,73.757 523.338,73.347 C521.94,72.803 520.942,72.155 519.894,71.106 C518.846,70.057 518.197,69.06 517.654,67.663 C517.244,66.606 516.755,65.022 516.623,62.101 C516.479,58.943 516.448,57.996 516.448,50 C516.448,42.003 516.479,41.056 516.623,37.899 C516.755,34.978 517.244,33.391 517.654,32.338 C518.197,30.938 518.846,29.942 519.894,28.894 C520.942,27.846 521.94,27.196 523.338,26.654 C524.393,26.244 525.979,25.756 528.898,25.623 C532.057,25.479 533.004,25.448 541,25.448 C548.997,25.448 549.943,25.479 553.102,25.623 C556.021,25.756 557.607,26.244 558.662,26.654 C560.06,27.196 561.058,27.846 562.106,28.894 C563.154,29.942 563.803,30.938 564.346,32.338 C564.756,33.391 565.244,34.978 565.378,37.899 C565.522,41.056 565.552,42.003 565.552,50 C565.552,57.996 565.522,58.943 565.378,62.101 M570.82,37.631 C570.674,34.438 570.167,32.258 569.425,30.349 C568.659,28.377 567.633,26.702 565.965,25.035 C564.297,23.368 562.623,22.342 560.652,21.575 C558.743,20.834 556.562,20.326 553.369,20.18 C550.169,20.033 549.148,20 541,20 C532.853,20 531.831,20.033 528.631,20.18 C525.438,20.326 523.257,20.834 521.349,21.575 C519.376,22.342 517.703,23.368 516.035,25.035 C514.368,26.702 513.342,28.377 512.574,30.349 C511.834,32.258 511.326,34.438 511.181,37.631 C511.035,40.831 511,41.851 511,50 C511,58.147 511.035,59.17 511.181,62.369 C511.326,65.562 511.834,67.743 512.574,69.651 C513.342,71.625 514.368,73.296 516.035,74.965 C517.703,76.634 519.376,77.658 521.349,78.425 C523.257,79.167 525.438,79.673 528.631,79.82 C531.831,79.965 532.853,80.001 541,80.001 C549.148,80.001 550.169,79.965 553.369,79.82 C556.562,79.673 558.743,79.167 560.652,78.425 C562.623,77.658 564.297,76.634 565.965,74.965 C567.633,73.296 568.659,71.625 569.425,69.651 C570.167,67.743 570.674,65.562 570.82,62.369 C570.966,59.17 571,58.147 571,50 C571,41.851 570.966,40.831 570.82,37.631"
                            ></path>
                          </g>
                        </g>
                      </g>
                    </svg>
                  </div>
                  <div style="padding-top: 8px">
                    <div
                      style="
                        color: #3897f0;
                        font-family: Arial, sans-serif;
                        font-size: 14px;
                        font-style: normal;
                        font-weight: 550;
                        line-height: 18px;
                      "
                    >
                      View this post on Instagram
                    </div>
                  </div>
                  <div style="padding: 12.5% 0"></div>
                  <div
                    style="
                      display: flex;
                      flex-direction: row;
                      margin-bottom: 14px;
                      align-items: center;
                    "
                  >
                    <div>
                      <div
                        style="
                          background-color: #f4f4f4;
                          border-radius: 50%;
                          height: 12.5px;
                          width: 12.5px;
                          transform: translateX(0px) translateY(7px);
                        "
                      ></div>
                      <div
                        style="
                          background-color: #f4f4f4;
                          height: 12.5px;
                          transform: rotate(-45deg) translateX(3px)
                            translateY(1px);
                          width: 12.5px;
                          flex-grow: 0;
                          margin-right: 14px;
                          margin-left: 2px;
                        "
                      ></div>
                      <div
                        style="
                          background-color: #f4f4f4;
                          border-radius: 50%;
                          height: 12.5px;
                          width: 12.5px;
                          transform: translateX(9px) translateY(-18px);
                        "
                      ></div>
                    </div>
                    <div style="margin-left: 8px">
                      <div
                        style="
                          background-color: #f4f4f4;
                          border-radius: 50%;
                          flex-grow: 0;
                          height: 20px;
                          width: 20px;
                        "
                      ></div>
                      <div
                        style="
                          width: 0;
                          height: 0;
                          border-top: 2px solid transparent;
                          border-left: 6px solid #f4f4f4;
                          border-bottom: 2px solid transparent;
                          transform: translateX(16px) translateY(-4px)
                            rotate(30deg);
                        "
                      ></div>
                    </div>
                    <div style="margin-left: auto">
                      <div
                        style="
                          width: 0px;
                          border-top: 8px solid #f4f4f4;
                          border-right: 8px solid transparent;
                          transform: translateY(16px);
                        "
                      ></div>
                      <div
                        style="
                          background-color: #f4f4f4;
                          flex-grow: 0;
                          height: 12px;
                          width: 16px;
                          transform: translateY(-4px);
                        "
                      ></div>
                      <div
                        style="
                          width: 0;
                          height: 0;
                          border-top: 8px solid #f4f4f4;
                          border-left: 8px solid transparent;
                          transform: translateY(-4px) translateX(8px);
                        "
                      ></div>
                    </div></div
                ></a>
                <p style="margin: 8px 0 0 0; padding: 0 4px">
                  <a
                    href="https://www.instagram.com/p/CE6Nls1gPbf/?utm_source=ig_embed&amp;utm_campaign=loading"
                    style="
                      color: #000;
                      font-family: Arial, sans-serif;
                      font-size: 14px;
                      font-style: normal;
                      font-weight: normal;
                      line-height: 17px;
                      text-decoration: none;
                      word-wrap: break-word;
                    "
                    target="_blank"
                    >Entrepreneurship is inherently ingrained within the
                    engineering trade. Many influential companies have been
                    founded by engineers, including Rolls-Royce, Dyson, Intel,
                    Oracle and Yahoo!, highlighting the power of the discipline
                    when seamlessly employed alongside core business ideals and
                    principles. “Innovation is the specific instrument of
                    entrepreneurship. The act that endows resources with a new
                    capacity to create wealth.” – Peter Drucker Check out the
                    link in the bio: Reasons Why Innovation and Entrepreneurship
                    in Engineering is Kind of a Big Deal.</a
                  >
                </p>
                <p
                  style="
                    color: #c9c8cd;
                    font-family: Arial, sans-serif;
                    font-size: 14px;
                    line-height: 17px;
                    margin-bottom: 0;
                    margin-top: 8px;
                    overflow: hidden;
                    padding: 8px 0 7px;
                    text-align: center;
                    text-overflow: ellipsis;
                    white-space: nowrap;
                  "
                >
                  A post shared by
                  <a
                    href="https://www.instagram.com/ieeeamu/?utm_source=ig_embed&amp;utm_campaign=loading"
                    style="
                      color: #c9c8cd;
                      font-family: Arial, sans-serif;
                      font-size: 14px;
                      font-style: normal;
                      font-weight: normal;
                      line-height: 17px;
                    "
                    target="_blank"
                  >
                    IEEE AMU</a
                  >
                  (@ieeeamu) on
                  <time
                    style="
                      font-family: Arial, sans-serif;
                      font-size: 14px;
                      line-height: 17px;
                    "
                    datetime="2020-09-09T08:45:44+00:00"
                    >Sep 9, 2020 at 1:45am PDT</time
                  >
                </p>
              </div>
            </blockquote>
            <script async src="//www.instagram.com/embed.js"></script>
          </v-card>
        </v-col>
      </v-row>
      <v-row>
        <v-card-text class="text-center" style="margin: 3rem auto"
          ><h1>Contact Us</h1></v-card-text
        >
        <v-col class="contact" cols="8" md="4"
          ><v-icon style="color: black" size="50">mdi-cellphone-iphone</v-icon>
          <h3 style="padding: 1rem 0">Phone</h3>
          <v-card-subtitle>9412690509</v-card-subtitle></v-col
        >
        <v-col class="contact" cols="8" md="4"
          ><v-icon style="color: black" size="50">mdi-email</v-icon>
          <h3 style="padding: 1rem 0">Email</h3>
          <v-card-subtitle>ieee-amu@gmail.com</v-card-subtitle></v-col
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
export default {
  components: {
    Spacer,
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
#about-us-1 {
  padding-top: 15px;
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
.contact {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  margin: auto;
}
</style>
