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
            <v-card-title v-text="card.title"></v-card-title>
          </v-img>
          <v-card-text v-text="card.text"></v-card-text>
          <v-row justify="center">
            <v-dialog v-model="dialog" width="600px">
              <v-spacer />
              <template v-slot:activator="{ on }">
                <v-btn id="know-more" v-on="on">Know more</v-btn>
              </template>
              <v-card>
                <v-card-title class="headline grey lighten-2 text-center">
                  {{ card.title }}
                </v-card-title>
                <v-card-text class="body-1 black--text font-weight-regular">{{
                  card.content
                }}</v-card-text>
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
        title: 'How to write a research paper',
        text: '24/09/2019',
        content:
        'The session was orated by Dr Khaliqur Rehman, Assistant Professor, Electrical Engineering Dept, ZHCET, AMU and attended by more than 170 students from various undergraduate and postgraduate courses. He began with the emphasis on the writing process and the structure of a research paper. His main focus was on proper planning and designing, evaluation and interpretation of data obtained, research ethics, statistical analysis  and the practical application of the writings. Dr Khaliq advised against publishing very old research papers, non-previewed publications and the use self cited old papers.The session was also marked by the doubts raised by the students.Mr Mohd.Zaid concluded the session and asked the students to interact with the office bearers of IEEE student’s branch for their queries.'
        src: 'https://cdn.vuetifyjs.com/images/cards/house.jpg'
      },
      {
        title: 'Solar panel',
        text: '18/10/2019',
        content:
        'The session was chaired by Dr.Adil Sarwar,Assistant Professor,Electrical Enginnering, AMU, Aligarh.He ia member of IEEE,USA and has published more than 40 research papers in the reputed journals. His research interest includes Power Convertors, Solar PV system and microcontrollers.Dr.Adil Sarwar explained about the Indian Scenario of solar energy, their structure and working principles. He discussed about the problems faced due to the over consumption of conventional sources. He discussed about various renewable resources of energry and urged the students to use them wisely.'
       src: 'https://cdn.vuetifyjs.com/images/cards/road.jpg'
      },
       {
        title: 'Internship',
        text: '07/03/2020',
        content:
          'The talk was delivered by Mr Mohammad Bilal, final year student of Civil Engineering. Being a summer intern at IIT Kanpur and a recipient of the prestigious MITACS fellowship, he encouraged the students about the fellowship.He also explained each step of application in detail and prerequisites the student must acquire for higher probability in selection to such research internship programs. He also enhanced the audience with the long term benefits of the MITACS internship program. Mr Jaffar A Lone concluded the talk with a thank you note.'
        src: 'https://cdn.vuetifyjs.com/images/cards/plane.jpg'
      },
      {
        title: 'Induction',
        text: '12/10/2019',
        content:
          'The orientation ceremony was conducted on 12th October,2019 with the welcome of the students,faculty members and was marked by the presence of Prof.Imtiaz Ashraf (HOD, Electrical Dept), Dr.Mohd.Rihan (Branch Coordinator), Mr.Mohd Zaid (Branch Counsellor) & other professors.The gathering was endorsed by the welcome note of Mr. Mohd Zaid and briefed about one of the biggest conferences in India i.e., "UPCON-2019".This was followed by Dr Mohd. Rihan who gave a presentation on origin and functioning of IEEE. Prof. Imtiaz Ashraf,then congratulated the office bearers and recapitulated the importance of IEEE. Next, Dr Adil Sarwar illuminated the audience about various societies and their roles. Mr Jaffar A. Lone (Chairperson) proposed the vote of thanks.'
        src: 'https://cdn.vuetifyjs.com/images/cards/plane.jpg'
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
</style>
