<template>
  <v-container>
    <v-row justify="center">
      <v-col cols="12" sm="10" md="8" lg="6">
        <v-card class="blue black--text">
          <div
            class="text-center headline pt-4 pb-4"
            style="font-family: 'Hammersmith One', sans-serif !important"
          >
            News Panel
          </div>
        </v-card>
      </v-col>
    </v-row>
    <v-row justify="center">
      <v-col
        v-for="event in news"
        :key="event.id"
        cols="12"
        sm="10"
        md="8"
        lg="6"
        :style="{ order: -event.order }"
      >
        <v-card class="mx-auto" max-width="344" elevation="3">
          <v-card-text>
            <p
              class="display-1 text--primary"
              style="font-family: 'Hammersmith One', sans-serif !important"
            >
              {{ event.title }}
            </p>
            <p>{{ event.date }}</p>
            <div class="text--primary">
              {{ event.text }}
            </div>
          </v-card-text>
          <v-card-actions>
            <v-btn
              :href="event.src"
              target="_blank"
              rel="noopener"
              color="orange"
              text
            >
              Learn More
            </v-btn>
          </v-card-actions>
        </v-card>
      </v-col>
    </v-row>
  </v-container>
</template>
<script>
export default {
  data() {
    return {
      news: [],
    }
  },
  created() {
    this.$fireStore
      .collection('news')
      .get()
      .then((querySnapshot) => {
        querySnapshot.forEach((doc) => {
          const docObj = doc.data()
          docObj.id = doc.id
          this.news.push(docObj)
        })
      })
  },
}
</script>
