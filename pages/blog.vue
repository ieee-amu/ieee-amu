<template>
  <v-container fluid>
    <v-row justify="center">
      <v-col v-for="card in cards" :key="card.title" cols="12">
        <v-card id="blog" class="mx-auto">
          <v-img
            :src="card.src"
            class="white--text align-end"
            gradient="to bottom, rgba(0,0,0,.1), rgba(0,0,0,.5)"
            height="400px"
          >
            <div class="justify-blog">{{ card.title }}</div>
          </v-img>
          <v-card-text v-text="card.text"></v-card-text>
          <v-row justify="center">
            <v-dialog v-model="dialog" width="600px">
              <v-spacer />
              <template v-slot:activator="{ on }">
                <v-btn id="know-more" v-on="on">Know more</v-btn>
              </template>
              <v-card>
                <div class="justify-blog grey lighten-2">
                  {{ card.title }}
                </div>
                <v-card-text class="body-1 black--text font-weight-regular">{{
                  card.content
                }}</v-card-text>
                <v-divider></v-divider>
                <v-card-actions>
                  <v-spacer></v-spacer>
                  <v-btn
                    :href="card.link"
                    target="_blank"
                    rel="noopener"
                    color="primary"
                    text
                  >
                    Read Full Report <v-icon>mdi-file-pdf-outline</v-icon>
                  </v-btn>
                </v-card-actions>
              </v-card>
            </v-dialog>
          </v-row>
        </v-card>
      </v-col>
    </v-row>
  </v-container>
</template>
<script>
export default {
  data: () => ({
    cards: [
      {
        title: 'WASTE HEAT MANAGEMENT AND ELECTRICITY  GENERATATION',
        text: '04/03/2020',
        content:
          'IEEE SIGHT student’s chapter (AMU) organised an informative session for the students of Women’s polytechnic, Aligarh Muslim University to spread awareness about the utilisation of technologies for Humanitarian causes and sustainable development. A lecture was delivered by Pakhil Singh, IEEE SIGHT Student Coordinator on “Waste Heat Management and Electricity Generation”. In this lecture, the utilisation and recovery of waste heat from exhausts of vehicles, outdoor units of Air conditioners, Power Plants, Refineries, heat wasted in aeroplane drag and their effective conversion into Electricity was discussed.',
        src:
          'https://www.greenbiz.com/sites/default/files/styles/gbz_article_primary_breakpoints_kalapicture_screen-lg_1x/public/images/articles/featured/partnership_0.jpg?itok=ZekH-so_&timestamp=1445488550',
        link:
          'https://drive.google.com/file/d/1OTsY4bfp0mvKBVOdkDrekGO-n0L91GF4/view?usp=sharing'
      },
      {
        title: 'INTERNSHIPS OPPURTUNITIES ABROAD',
        text: '04/03/2020',
        content:
          'The talk was delivered by Mr Mohammad Bilal, final year student of Civil Engineering. Being a summer intern at IIT Kanpur and a recipient of the prestigious MITACS fellowship, he encouraged the students about the fellowship. He also explained each step of application in detail and prerequisites the student must acquire for higher probability in selection to such research internship programs. He also enhanced the audience with the long term benefits of the MITACS internship program. Mr Jaffar A Lone concluded the talk with a thank you note.',
        src: 'https://firebasestorage.googleapis.com/v0/b/ieee-amu.appspot.com/o/internship_abroad.jpg?alt=media&token=3cb8c4af-8f46-4659-aa3a-1f58f2ed5951',
        link:
          'https://drive.google.com/file/d/1otdc6ihbFMH4nS85oodYsGFLgYK__C4e/view?usp=sharing'
      },
      {
        title: 'MAXIMUM POWER POINT TRACKING IN A SOLAR PV GENERATION SYSTEM',
        text: '20/11/2019',
        content:
          'The session was chaired by Dr. Adil Sarwar, Assistant Professor, Electrical Enginnering, AMU, Aligarh. He is a member of IEEE, USA and has published more than 40 research papers in the reputed journals. His research interest includes Power Convertors, Solar PV system and microcontrollers. Dr. Adil Sarwar explained about the Indian Scenario of solar energy, their structure and working principles. He discussed about the problems faced due to the over consumption of conventional sources. He discussed about various renewable resources of energry and urged the students to use them wisely.',
        src: 'https://firebasestorage.googleapis.com/v0/b/ieee-amu.appspot.com/o/solarpanel.jpg?alt=media&token=a1d656a5-b118-4728-a4b0-66d91ab5d235',
        link:
          'https://drive.google.com/file/d/1_wADgE8Hwpoa0kouGztF-K-tEC-RBQlp/view?usp=sharing'
      },
      {
        title: 'ETHICS OF WRITING A RESEARCH PAPER',
        text: '23/10/2019',
        content:
          'The session was orated by Dr Khaliqur Rehman, Assistant Professor, Electrical Engineering Dept, ZHCET, AMU and attended by more than 170 students from various undergraduate and postgraduate courses. He began with the emphasis on the writing process and the structure of a research paper. His main focus was on proper planning and designing, evaluation and interpretation of data obtained, research ethics, statistical analysis  and the practical application of the writings. Dr Khaliq advised against publishing very old research papers, non-previewed publications and the use self cited old papers. The session was also marked by the doubts raised by the students. Mr Mohd. Zaid concluded the session and asked the students to interact with the office bearers of IEEE student’s branch for their queries.',
        src: 'https://firebasestorage.googleapis.com/v0/b/ieee-amu.appspot.com/o/researchpaper.jpg?alt=media&token=aaa05245-4761-4f84-85ce-998710830c5d',
        link:
          'https://drive.google.com/file/d/1PdtuxIAXIQ665nz4-AofiS4PVA2TNtBj/view?usp=sharing'
      },
      {
        title: 'Orientation Ceremony, 2019-20',
        text: '12/10/2019',
        content:
          'The orientation ceremony was conducted on 12th October, 2019 with the welcome of the students, faculty members and was marked by the presence of Prof. Imtiaz Ashraf (HOD, Electrical Dept), Dr.Mohd.Rihan (Branch Coordinator), Mr.Mohd Zaid (Branch Counsellor) & other professors. The gathering was endorsed by the welcome note of Mr. Mohd Zaid and briefed about one of the biggest conferences in India i.e., "UPCON-2019". This was followed by Dr Mohd. Rihan who gave a presentation on origin and functioning of IEEE. Prof. Imtiaz Ashraf, then congratulated the office bearers and recapitulated the importance of IEEE. Next, Dr Adil Sarwar illuminated the audience about various societies and their roles. Mr Jaffar A. Lone (Chairperson) proposed the vote of thanks.',
        src: 'https://firebasestorage.googleapis.com/v0/b/ieee-amu.appspot.com/o/orientation.jpg?alt=media&token=fb460c14-2562-4231-adcd-bd5e8806d98c',
        link:
          'https://drive.google.com/file/d/1-X3pHjmCYuBTOntm_cKdpVH8JbfhjKFa/view?usp=sharing'
      }
    ]
  })
}
</script>
<style scoped>
#know-more {
  padding: auto;
  margin-bottom: 10px;
}
#blog {
  margin-bottom: 20px;
  margin-top: 10px;
}
.justify-blog {
  text-align: center;
  text-justify: inter-word;
  font-size: 20px;
  font-weight: 550;
  margin-bottom: 20px;
  margin-top: 20px;
  padding-left: 2px;
}
</style>
