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
              lazy-src="https://www.aminz.org.nz/themes/portal/uploads/profile-default-large.jpg"
            >
              <template v-slot:placeholder>
                <v-row class="fill-height ma-0" align="center" justify="center">
                  <v-progress-circular
                    indeterminate
                    color="grey lighten-5"
                  ></v-progress-circular>
                </v-row>
              </template>
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
        title: 'Prof. M. M. Sufyan Beg',
        text: 'Principal',
        src:
          'https://firebasestorage.googleapis.com/v0/b/ieee-amu.appspot.com/o/sufiyan.jpeg?alt=media&token=f6c93551-2707-4379-a5e5-762fdcbd5042'
      },
      {
        title: 'Dr. Mohd Rihan',
        text: 'Branch Coordinator',
        src:
          'https://firebasestorage.googleapis.com/v0/b/ieee-amu.appspot.com/o/rehan.jpeg?alt=media&token=e843047c-228f-4234-acc2-e7f92a25f30a'
      },
      {
        title: 'Mr. Mohammad Zaid',
        text: 'Branch Counsellor',
        src:
          'https://firebasestorage.googleapis.com/v0/b/ieee-amu.appspot.com/o/zaid.jpg?alt=media&token=5546cd39-6a18-4c0a-985f-d7205d69a97a'
      },
      {
        title: 'Jaffar Ali Lone',
        text: 'Chairperson',
        src:
          'https://firebasestorage.googleapis.com/v0/b/ieee-amu.appspot.com/o/jaffer-min.jpg?alt=media&token=7ce520dc-5489-497f-992b-9293a1c93d8c'
      },
      {
        title: 'Asadullah Khan',
        text: 'Vice-Chairperson',
        src:
          'https://firebasestorage.googleapis.com/v0/b/ieee-amu.appspot.com/o/asad-min.jpg?alt=media&token=356963d5-33f8-43a8-be2e-dd25ab94ee35'
      },
      {
        title: 'Syed Zubair Ali',
        text: 'Secretary',
        src:
          'https://firebasestorage.googleapis.com/v0/b/ieee-amu.appspot.com/o/zubair.jpg?alt=media&token=b7e9d986-84e6-465c-b921-ad60da59c398'
      },
      {
        title: 'Abbas Syed Nooruddin',
        text: 'Joint-Secretary',
        src:
          'https://firebasestorage.googleapis.com/v0/b/ieee-amu.appspot.com/o/abbas-min.jpg?alt=media&token=ce8b429c-da87-481b-96f6-95883889a120'
      },
      {
        title: 'Shahrukh Khan',
        text: 'Treasurer',
        src:
          'https://firebasestorage.googleapis.com/v0/b/ieee-amu.appspot.com/o/shahrukh.jpg?alt=media&token=880fb247-f644-4fbb-a417-d4741f5cf0f6'
      },
      {
        title: 'Arushi Varshney',
        text: 'Coordinator (Membership Drive)',
        src:
          'https://firebasestorage.googleapis.com/v0/b/ieee-amu.appspot.com/o/arushi-min.jpg?alt=media&token=eb3b66d1-3d13-44c9-96db-34a66c3c456f'
      },
      {
        title: 'Pakhil Singh',
        text: 'Coordinator (SIGHT)',
        src:
          'https://firebasestorage.googleapis.com/v0/b/ieee-amu.appspot.com/o/pakhil.JPG?alt=media&token=7e2d506a-f84c-44ff-a3ee-f4a12f2ac84a'
      },
      {
        title: 'Hina Tomar',
        text: 'Coordinator (Media Interaction)',
        src:
          'https://firebasestorage.googleapis.com/v0/b/ieee-amu.appspot.com/o/hina-min.jpg?alt=media&token=945d17c2-46ba-43b8-bc53-15b6bf056ca6'
      },
      {
        title: 'Rashid Ahmed Khan',
        text: 'Coordinator (Media Interaction)',
        src:
          'https://firebasestorage.googleapis.com/v0/b/ieee-amu.appspot.com/o/rashid.jpg?alt=media&token=d7d05f44-d901-4cc4-ba54-6766499e58e9'
      }
    ]
  })
}
</script>
