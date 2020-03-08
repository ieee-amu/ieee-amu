<template>
  <v-container>
    <v-row justify="center">
      <v-col cols="10" sm="6">
        <v-card color="rgba(182, 187, 165, 1)">
          <v-card-text class="text-center headline black--text">
            Our Team
          </v-card-text>
        </v-card>
      </v-col>
    </v-row>
    <spacer gap="3" />
    <v-divider />
    <spacer gap="3" />
    <v-container>
      <v-row justify="space-between">
        <v-col v-for="card in cards" :key="card.title">
          <v-card>
            <v-img
              :src="card.src"
              class="white--text align-end"
              gradient="to bottom, rgba(0,0,0,.1), rgba(0,0,0,.5)"
              height="300px"
              max-width="350px"
              position="center"
            >
              <v-card-title v-text="card.title"></v-card-title>
            </v-img>
            <v-card-text v-text="card.text" class="blockquote"></v-card-text>
          </v-card>
        </v-col>
      </v-row>
    </v-container>
  </v-container>
</template>
<script>
import Spacer from '@/components/Spacer'

export default {
  components: {
    Spacer
  },
  data: () => ({
    cards: [
      {
        title: 'Duddu boy',
        text: 'Owner',
        src: 'https://avatars3.githubusercontent.com/u/49076836?s=400&v=4'
      },
      {
        title: 'Duddu boy',
        text: 'Owner',
        src: 'https://avatars3.githubusercontent.com/u/49076836?s=400&v=4'
      },
      {
        title: 'Duddu boy',
        text: 'Owner',
        src: 'https://avatars3.githubusercontent.com/u/49076836?s=400&v=4'
      },
      {
        title: 'Duddu boy',
        text: 'Owner',
        src: 'https://avatars3.githubusercontent.com/u/49076836?s=400&v=4'
      },
      {
        title: 'Duddu boy',
        text: 'Owner',
        src: 'https://avatars3.githubusercontent.com/u/49076836?s=400&v=4'
      },
      {
        title: 'Duddu boy',
        text: 'Owner',
        src: 'https://avatars3.githubusercontent.com/u/49076836?s=400&v=4'
      },
      {
        title: 'Duddu boy',
        text: 'Owner',
        src: 'https://avatars3.githubusercontent.com/u/49076836?s=400&v=4'
      }
    ]
  })
}
</script>
