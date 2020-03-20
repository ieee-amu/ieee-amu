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
            Welcome to IEEE-AMU, A community of erudite and professorial
            individuals whose purpose is to disseminate knowledge on technical
            works, seminars, conferences and accreditations while advocating
            benefits to its members. Being the world's largest technical
            profeesional society, IEEE's benfits include venues and tools for
            members to network, build valuable profeesional connections, and
            leadership skills.
            <br />
            <br />
            Thank you for stopping by IEEE-AMU
          </p>
        </v-text>
      </v-card>
    </v-container>
    <v-container>
      <v-row justify="center">
        <v-col cols="12" sm="12">
          <v-card color="rgba(53, 177, 208, 1)">
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
          <v-card :to="`/team`" shaped color="rgba(230, 223, 148, 1)">
            <v-card-text class="text-center headline">
              Team
            </v-card-text>
          </v-card>
        </v-col>

        <v-col cols="10" sm="4">
          <v-card :to="`/blog`" shaped color="rgba(144, 131, 226, 1)">
            <v-card-text class="text-center headline">
              Blogs
            </v-card-text>
          </v-card>
        </v-col>

        <v-col cols="10" sm="4">
          <v-card :to="`/contact`" shaped color="rgba(235, 168, 235, 1)">
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
<style scoped>
#about-us-1 {
  padding-top: 15px;
}
#about-us-2 {
  text-align: justify;
  margin-left: 50px;
  margin-right: 50px;
  padding: 10px;
}
</style>
