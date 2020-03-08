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
            Lorem ipsum dolor sit amet consectetur adipisicing elit. Beatae
            expedita exercitationem vitae qui fugit totam quam eos alias ullam
            obcaecati, nostrum nemo odio recusandae! Laboriosam ipsa nesciunt
            sunt neque recusandae. Lorem ipsum dolor sit amet, consectetur
            adipisicing elit. Quam culpa ad est debitis, dolor a quibusdam non
            perspiciatis fugiat odio rem, blanditiis facilis repudiandae. Sint
            ab suscipit reprehenderit a quidem! Lorem ipsum dolor, sit amet
            consectetur adipisicing elit. Quisquam repellendus adipisci
            voluptatum architecto nemo qui unde repellat sequi suscipit sint
            iure sed minima quis aspernatur sapiente error corporis, earum quas?
          </p>
        </v-text>
      </v-card>
    </v-container>
    <v-container>
      <v-row justify="center">
        <v-col cols="10" sm="6">
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
      <v-row align="center">
        <v-col class="text-center" cols="12" sm="4">
          <div class="my-2">
            <v-btn :to="`/team`" x-large rounded color="rgba(144, 131, 226, 1)"
              >Team</v-btn
            >
          </div>
        </v-col>

        <v-col class="text-center" cols="12" sm="4">
          <div class="my-2">
            <v-btn :to="`/blog`" x-large rounded color="rgba(230, 223, 148, 1)"
              >Blogs</v-btn
            >
          </div>
        </v-col>

        <v-col class="text-center" cols="12" sm="4">
          <div class="my-2">
            <v-btn
              :to="`/contact`"
              x-large
              rounded
              color="rgba(235, 168, 235, 1)"
              >Contacts</v-btn
            >
          </div>
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
