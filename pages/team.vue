<template>
  <v-container>
    <v-row justify="center">
      <v-col cols="10" sm="6">
        <v-card color="rgba(182, 187, 165, 1)">
          <v-card-text class="text-center headline black--text">
            FACULTY ADVISORS
          </v-card-text>
        </v-card>
      </v-col>
    </v-row>
    <spacer gap="3" />
    <v-container>
      <v-row justify="space-between">
        <v-col v-for="faculty in faculties" :key="faculty.title" cols="auto">
          <v-card>
            <v-img
              :src="faculty.src"
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
              <v-card-title v-text="faculty.title"></v-card-title>
            </v-img>
            <v-card-text v-text="faculty.text" class="blockquote"></v-card-text>
            <v-col class="lighten-3 text-center pa-0">
              <v-btn
                v-for="(link, type) in faculty.links"
                :key="type"
                :color="iconColor(type)"
                class="mx-3 my-2"
                fab
                dark
                small
              >
                <a
                  :href="getLink(link, type)"
                  target="_blank"
                  rel="noopener"
                  style="text-decoration: none; color: inherit"
                >
                  <v-icon dark size="18">{{ icon(type) }}</v-icon>
                </a>
              </v-btn>
            </v-col>
          </v-card>
        </v-col>
      </v-row>
    </v-container>
    <spacer gap="3" />
    <v-divider></v-divider>
    <spacer gap="3" />
    <v-row justify="center">
      <v-col cols="10" sm="6">
        <v-card color="rgba(182, 187, 165, 1)">
          <v-card-text class="text-center headline black--text">
            OFFICE BEARERS
          </v-card-text>
        </v-card>
      </v-col>
    </v-row>
    <spacer gap="3" />
    <v-container>
      <v-row justify="space-between">
        <v-col v-for="student in students" :key="student.title" cols="auto">
          <v-card>
            <v-img
              :src="student.src"
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
              <v-card-title v-text="student.title"></v-card-title>
            </v-img>
            <v-card-text v-text="student.text" class="blockquote"></v-card-text>
            <v-col class="lighten-3 text-center pa-0">
              <v-btn
                v-for="(link, type) in student.links"
                :key="type"
                :color="iconColor(type)"
                class="mx-3 my-2"
                fab
                dark
                small
              >
                <a
                  :href="getLink(link, type)"
                  target="_blank"
                  rel="noopener"
                  style="text-decoration: none; color: inherit"
                >
                  <v-icon dark size="18">{{ icon(type) }}</v-icon>
                </a>
              </v-btn>
            </v-col>
          </v-card>
        </v-col>
      </v-row>
    </v-container>
    <spacer gap="3" />
    <v-divider></v-divider>
    <spacer gap="3" />
    <v-row justify="center">
      <v-col cols="10" sm="6">
        <v-card color="rgba(182, 187, 165, 1)">
          <v-card-text class="text-center headline black--text">
            VOLUNTEERS
          </v-card-text>
        </v-card>
      </v-col>
    </v-row>
    <spacer gap="3" />
    <v-container>
      <v-row justify="space-between">
        <v-col
          v-for="volunteer in volunteers"
          :key="volunteer.title"
          cols="auto"
        >
          <v-card>
            <v-img
              :src="volunteer.src"
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
              <v-card-title v-text="volunteer.title"></v-card-title>
            </v-img>
            <v-col class="lighten-3 text-center pa-0">
              <v-btn
                v-for="(link, type) in volunteer.links"
                :key="type"
                :color="iconColor(type)"
                class="mx-3 my-2"
                fab
                dark
                small
              >
                <a
                  :href="getLink(link, type)"
                  target="_blank"
                  rel="noopener"
                  style="text-decoration: none; color: inherit"
                >
                  <v-icon dark size="18">{{ icon(type) }}</v-icon>
                </a>
              </v-btn>
            </v-col>
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
    students: [
      {
        title: 'Jaffar Ali Lone',
        text: 'Chairperson',
        links: {
          email: 'jalone@myamu.ac.in',
          mobile: '+919682606700',
          linkedin: 'https://linkedin.com/in/jaffar-ali-lone-958128129'
        },
        src:
          'https://firebasestorage.googleapis.com/v0/b/ieee-amu.appspot.com/o/jaffer-min.jpg?alt=media&token=7ce520dc-5489-497f-992b-9293a1c93d8c'
      },
      {
        title: 'Asadullah Khan',
        text: 'Vice-Chairperson',
        links: {
          email: 'Asadkhan1550899@gmail.com',
          mobile: '+919045690938',
          linkedin:
            'https://www.linkedin.com/mwlite/in/asadullah-khan-83944115a'
        },
        src:
          'https://firebasestorage.googleapis.com/v0/b/ieee-amu.appspot.com/o/asad-min.jpg?alt=media&token=356963d5-33f8-43a8-be2e-dd25ab94ee35'
      },
      {
        title: 'Syed Zubair Ali',
        text: 'Secretary',
        links: {
          email: 'zubairali28.zhcet@gmail.com',
          mobile: '+919412690509',
          linkedin: 'https://www.linkedin.com/in/zubair-ali-b551a2179'
        },
        src:
          'https://firebasestorage.googleapis.com/v0/b/ieee-amu.appspot.com/o/zubair.jpg?alt=media&token=b7e9d986-84e6-465c-b921-ad60da59c398'
      },
      {
        title: 'Abbas Syed Nooruddin',
        text: 'Joint-Secretary',
        links: {
          email: 'abbasnooruddin02@gmail.com',
          linkedin: 'https://www.linkedin.com/in/abbas-nooruddin-a0a68a19a'
        },
        src:
          'https://firebasestorage.googleapis.com/v0/b/ieee-amu.appspot.com/o/abbas-min.jpg?alt=media&token=ce8b429c-da87-481b-96f6-95883889a120'
      },
      {
        title: 'Shahrukh Khan',
        text: 'Treasurer',
        links: {
          email: 'khansrk9452971632@gmail.com',
          linkedin: 'https://www.linkedin.com/in/shahrukh-khan-24711217b'
        },
        src:
          'https://firebasestorage.googleapis.com/v0/b/ieee-amu.appspot.com/o/shahrukh.jpg?alt=media&token=880fb247-f644-4fbb-a417-d4741f5cf0f6'
      },
      {
        title: 'Arushi Varshney',
        text: 'Coordinator (Membership Drive)',
        links: {
          email: 'arushi21varshney@gmail.com',
          linkedin: 'https://www.linkedin.com/in/arushi-varshney-379428166'
        },
        src:
          'https://firebasestorage.googleapis.com/v0/b/ieee-amu.appspot.com/o/arushi.jpg?alt=media&token=1571a78e-41c1-4fd3-a31f-ea20c0c63bc9'
      },
      {
        title: 'Pakhil Singh',
        text: 'Coordinator (SIGHT)',
        links: {
          email: 'pakhilsingh171998@gmail.com',
          linkedin: 'https://www.linkedin.com/in/pakhil-singh-59995715a'
        },
        src:
          'https://firebasestorage.googleapis.com/v0/b/ieee-amu.appspot.com/o/pakhil.JPG?alt=media&token=7e2d506a-f84c-44ff-a3ee-f4a12f2ac84a'
      },
      {
        title: 'Hina Tomar',
        text: 'Coordinator (Media Interaction)',
        links: {
          email: 'hinatomar868@gmail.com',
          linkedin: 'https://www.linkedin.com/in/hinatomar22'
        },
        src:
          'https://firebasestorage.googleapis.com/v0/b/ieee-amu.appspot.com/o/hina-min.jpg?alt=media&token=945d17c2-46ba-43b8-bc53-15b6bf056ca6'
      },
      {
        title: 'Rashid Ahmed Khan',
        text: 'Coordinator (Media Interaction)',
        links: {
          email: 'rakhan@myamu.ac.in',
          mobile: '+918265820477',
          linkedin: 'https://www.linkedin.com/in/rashidkhanamu'
        },
        src:
          'https://firebasestorage.googleapis.com/v0/b/ieee-amu.appspot.com/o/rashid.jpg?alt=media&token=d7d05f44-d901-4cc4-ba54-6766499e58e9'
      }
    ],
    faculties: [
      {
        title: 'Prof. M. M. Sufyan Beg',
        text: 'Principal',
        links: { email: 'mmsbeg@cs.berkeley.edu' },
        src:
          'https://firebasestorage.googleapis.com/v0/b/ieee-amu.appspot.com/o/sufiyan.jpeg?alt=media&token=f6c93551-2707-4379-a5e5-762fdcbd5042'
      },
      {
        title: 'Dr. Mohd Rihan',
        text: 'Branch Coordinator',
        links: { email: 'm.rihan.ee@amu.ac.in' },
        src:
          'https://firebasestorage.googleapis.com/v0/b/ieee-amu.appspot.com/o/rehan.jpeg?alt=media&token=e843047c-228f-4234-acc2-e7f92a25f30a'
      },
      {
        title: 'Dr. Mohd Tariq',
        text: 'Branch Coordinator',
        links: { email: 'tariq.iitkgp@gmail.com' },
        src:
          'https://firebasestorage.googleapis.com/v0/b/ieee-amu.appspot.com/o/tariq.jpg?alt=media&token=1f7b407d-1b8f-41f8-a2fb-9a134a0fb00d'
      },
      {
        title: 'Mr. Mohammad Zaid',
        text: 'Branch Counsellor',
        links: { email: 'MOHAMMAD.ZAID@zhcet.ac.in' },
        src:
          'https://firebasestorage.googleapis.com/v0/b/ieee-amu.appspot.com/o/zaid.jpg?alt=media&token=5546cd39-6a18-4c0a-985f-d7205d69a97a'
      }
    ],
    volunteers: [
      {
        title: 'Nidhi Chawla',
        links: {
          email: 'nidhichawla951@gmail.com',
          linkedin: 'https://www.linkedin.com/in/nidhi-chawla-a644b01b1'
        },
        src: 'http://i.xp.io/1pIRaiiD.png'
      },
      {
        title: 'Yusra Amir',
        links: {
          email: 'amiryusra0571@gmail.com',
          linkedin: 'https://www.linkedin.com/in/yusra-amir-33805517a'
        },
        src: 'http://i.xp.io/1pJawHA3.jpg'
      },
      {
        title: 'Kunal Sharma',
        links: {
          email: 'kcunalsharma@gmail.com',
          mobile: '9639025077',
          linkedin: 'https://www.linkedin.com/in/kunal-sharma-b757021a1'
        },
        src: 'http://i.xp.io/1pJ8bQsK.jpg'
      },
      {
        title: 'Sharib Ahmed',
        links: {
          email: 'msharibahmed@gmail.com',
          mobile: '8052889228',
          linkedin: 'https://www.linkedin.com/in/sharib-ahmed-b3b930174'
        },
        src: 'http://i.xp.io/1pJ5TiyY.jpg'
      },
      {
        title: 'Aditya Mishra',
        links: {
          email: 'm.aditya.a7459@gmail.com',
          mobile: '7459952961',
          linkedin: 'https://www.linkedin.com/in/aditya-mishra-839726182'
        },
        src: 'http://i.xp.io/1pJ3AxMg.jpg'
      },
      {
        title: 'Mahena Mahmood',
        links: {
          email: 'mahenak.2@gmail.com',
          linkedin: 'https://www.linkedin.com/in/mahena-mahmood-8b77321b1'
        },
        src: 'http://i.xp.io/1pKH6mPD.jpg'
      },
      {
        title: 'Laiba Sagheer',
        links: {
          email: 'sagheerlaiba124@gmail.com',
          linkedin: 'https://www.linkedin.com/in/laiba-sagheer-10a994180'
        },
        src:
          'https://www.aminz.org.nz/themes/portal/uploads/profile-default-large.jpg'
      }
    ]
  }),
  methods: {
    iconColor(type) {
      switch (type) {
        case 'facebook':
          return 'blue darken-4'
        case 'email':
          return 'red darken-1'
        case 'g-plus':
          return 'red darken-4'
        case 'linkedin':
          return 'indigo darken-1'
        case 'mobile':
          return 'green darken-3'
        case 'twitter':
          return 'light-blue darken-1'
        case 'github':
          return 'black'
      }
    },
    icon(type) {
      switch (type) {
        case 'g-plus':
          return 'mdi-google-plus'
        case 'mobile':
          return 'mdi-phone'
        default:
          return `mdi-${type}`
      }
    },
    getLink(link, type) {
      if (type === 'email') {
        return 'mailto:' + link
      } else if (type === 'mobile') {
        return 'tel:' + link
      } else if (!link.startsWith('http://') && !link.startsWith('https://')) {
        return '//' + link
      }
      return link
    }
  }
}
</script>
