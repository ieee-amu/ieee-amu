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
        <v-text class="card-text">
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
        </v-text>
      </v-card>
      <v-row dense>
        <!-- prettier-ignore -->
        <v-img
          contain
          src="https://firebasestorage.googleapis.com/v0/b/ieee-amu.appspot.com/o/ieee.jpeg?alt=media&token=230d055f-f6c7-48ea-879e-4cfe63ac994b"
          width="250px"
          height="250px"
        >
        </v-img>
        <!-- prettier-ignore -->
        <v-img
          contain
          src="https://firebasestorage.googleapis.com/v0/b/ieee-amu.appspot.com/o/amu.jpeg?alt=media&token=2ef08fee-fb64-4559-b20d-0cf9e9a58b09"
          width="250px"
          height="250px"
        >
        </v-img>
      </v-row>
    </v-container>
    <v-container>
      <v-row justify="center">
        <v-col cols="12" sm="12">
          <v-card color="rgba(157, 201, 231, 1)">
            <v-card-text class="text-center headline black--text">
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
          <v-card :to="`/team`" shaped color="rgba(245, 195, 173, 1)">
            <v-card-text class="text-center headline">
              Team
            </v-card-text>
          </v-card>
        </v-col>

        <v-col cols="10" sm="4">
          <v-card :to="`/blog`" shaped color="rgba(173, 235, 183, 1)">
            <v-card-text class="text-center headline">
              Blogs
            </v-card-text>
          </v-card>
        </v-col>

        <v-col cols="10" sm="4">
          <v-card :to="`/contact`" shaped color="rgba(251, 219, 247, 1)">
            <v-card-text class="text-center headline">
              Contacts
            </v-card-text>
          </v-card>
        </v-col>
      </v-row>
    </v-container>
  </div>
</template>

<script>
import Spacer from '@/components/Spacer'

export default {
  components: {
    Spacer
  },
  data() {
    return {
      items: [
        {
          src:
            'https://firebasestorage.googleapis.com/v0/b/ieee-amu.appspot.com/o/carousel6.jpg?alt=media&token=66f1c6c6-bd59-4338-827b-08e41684d89e'
        },
        {
          src:
            'https://firebasestorage.googleapis.com/v0/b/ieee-amu.appspot.com/o/carousel.jpeg?alt=media&token=3d78298d-d66b-413c-9154-9c33b7420257'
        },
        {
          src:
            'https://firebasestorage.googleapis.com/v0/b/ieee-amu.appspot.com/o/carousel4.jpeg?alt=media&token=f0d73c2d-4705-4f0f-9645-d1feec377869'
        },
        {
          src:
            'https://firebasestorage.googleapis.com/v0/b/ieee-amu.appspot.com/o/carousel2.jpeg?alt=media&token=5b481cdd-3e5c-44fc-9937-ee177c63a886'
        },
        {
          src:
            'https://firebasestorage.googleapis.com/v0/b/ieee-amu.appspot.com/o/carousel3.jpeg?alt=media&token=49967e25-b6e9-4cac-a7f1-1dfd691023e9'
        }
      ]
    }
  }
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
