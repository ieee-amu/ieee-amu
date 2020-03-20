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
        <v-col v-for="card in cards" :key="card.title" cols="auto">
          <v-card>
            <v-img
              :src="card.src"
              class="white--text align-end"
              gradient="to bottom, rgba(0,0,0,.1), rgba(0,0,0,.5)"
              height="310px"
              max-width="310px"
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
        title: 'Jaffar Ali Lone',
        text: 'Chairperson',
        src: 'jaffer.jpg'
      },
      {
        title: 'Asadullah Khan',
        text: 'Vice-Chairperson',
        src: 'asad.jpg'
      },
      {
        title: 'Syed Zubair Ali',
        text: 'Secretary',
        src: 'zubair.jpg'
      },
      {
        title: 'Abbas Syed Nooruddin',
        text: 'Joint-Secretary',
        src: 'abbas.jpg'
      },
      {
        title: 'Shahrukh Khan',
        text: 'Treasurer',
        src: 'https://avatars0.githubusercontent.com/u/40136154?s=460&v=4'
      },
      {
        title: 'Arushi Varshney',
        text: 'Coordinator (Membership Drive)',
        src: 'arushi.jpg'
      },
      {
        title: 'Pakhil Singh',
        text: 'Coordinator (SIGHT)',
        src: 'pakhil.jpg'
      },
      {
        title: 'Hina Tomar',
        text: 'Coordinator (Media Interaction)',
        src: 'https://avatars0.githubusercontent.com/u/40136154?s=460&v=4'
      },
      {
        title: 'Rashid Ahmed Khan',
        text: 'Coordinator (Media Interaction)',
        src: 'rashid.jpg'
      }
    ]
  })
}
</script>
