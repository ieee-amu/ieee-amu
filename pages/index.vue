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
          <p id="about-us-1" class="display-2">
            About Us
          </p>
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
    <Calendar />
    <v-container>
      <v-row justify="center">
        <v-col cols="12" sm="12">
          <v-card color="rgba(74, 74, 74, 1)">
            <v-card-text class="text-center white--text headline">
              Know more about us
            </v-card-text>
          </v-card>
        </v-col>
      </v-row>
      <spacer gap="1" />
      <v-divider />
    </v-container>
    <v-container>
      <v-row justify="center">
        <v-col cols="10" sm="4">
          <v-card :to="`/team`" shaped color="rgba(74, 74, 74, 1)">
            <v-card-text class="text-center white--text headline">
              Team
            </v-card-text>
          </v-card>
        </v-col>

        <v-col cols="10" sm="4">
          <v-card :to="`/blog`" shaped color="rgba(74, 74, 74, 1)">
            <v-card-text class="text-center white--text headline">
              Blogs
            </v-card-text>
          </v-card>
        </v-col>

        <v-col cols="10" sm="4">
          <v-card
            to="/contact"
            target="_blank"
            rel="noopener"
            shaped
            color="rgba(74, 74, 74, 1)"
          >
            <v-card-text class="text-center white--text headline">
              Contact Us
            </v-card-text>
          </v-card>
        </v-col>
      </v-row>
    </v-container>
  </div>
</template>

<script>
import Spacer from '@/components/Spacer'
import Calendar from '@/components/Calendar'

export default {
  components: {
    Spacer,
    Calendar,
  },
  data() {
    return {
      items: [
        {
          src:
            'https://firebasestorage.googleapis.com/v0/b/ieee-amu.appspot.com/o/default.png?alt=media&token=62b294ec-f592-43ea-850b-58509fda3d22',
        },
        {
          src:
            'https://firebasestorage.googleapis.com/v0/b/ieee-amu.appspot.com/o/carousel.jpeg?alt=media&token=3d78298d-d66b-413c-9154-9c33b7420257',
        },
        {
          src:
            'https://firebasestorage.googleapis.com/v0/b/ieee-amu.appspot.com/o/carousel4.jpeg?alt=media&token=f0d73c2d-4705-4f0f-9645-d1feec377869',
        },
        {
          src:
            'https://firebasestorage.googleapis.com/v0/b/ieee-amu.appspot.com/o/carousel2.jpeg?alt=media&token=5b481cdd-3e5c-44fc-9937-ee177c63a886',
        },
        {
          src:
            'https://firebasestorage.googleapis.com/v0/b/ieee-amu.appspot.com/o/carousel3.jpeg?alt=media&token=49967e25-b6e9-4cac-a7f1-1dfd691023e9',
        },
      ],
    }
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
</style>
