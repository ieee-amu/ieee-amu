<template>
  <v-card class="mx-auto" max-width="800">
    <v-container fluid>
      <v-row dense>
        <v-col v-for="card in cards" :key="card.title" :cols="card.flex">
          <v-card elevation="10">
            <v-img
              :src="card.src"
              class="white--text align-end"
              gradient="to bottom, rgba(0,0,0,.1), rgba(0,0,0,.5)"
              height="400px"
            >
              <v-card-title v-text="card.title"></v-card-title>
            </v-img>
            <v-card-text v-text="card.text"></v-card-text>
            <v-card-actions>
              <v-spacer></v-spacer>
              <v-btn>Know more</v-btn>
            </v-card-actions>
          </v-card>
        </v-col>
      </v-row>
    </v-container>
  </v-card>
</template>
<script>
export default {
  data: () => ({
    cards: [
      {
        title: 'How to write a research paper',
        text: 'hello world',
        src: 'https://cdn.vuetifyjs.com/images/cards/house.jpg',
        flex: 12
      },
      {
        title: 'Solar panel',
        text: 'hello world',
        src: 'https://cdn.vuetifyjs.com/images/cards/road.jpg',
        flex: 6
      },
      {
        title: 'Induction',
        text: 'hello world',
        src: 'https://cdn.vuetifyjs.com/images/cards/plane.jpg',
        flex: 6
      },
      {
        title: 'Internship',
        text: 'hello world',
        src: 'https://cdn.vuetifyjs.com/images/cards/plane.jpg',
        flex: 12
      }
    ]
  })
}
</script>
