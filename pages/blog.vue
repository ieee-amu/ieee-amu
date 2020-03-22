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
          'Lorem ipsum dolor sit amet consectetur adipisicing elit. Beatae expedita exercitationem vitae qui fugit totam quam eos alias ullam obcaecati, nostrum nemo odio recusandae! Laboriosam ipsa nesciunt sunt neque recusandae. Lorem ipsum dolor sit amet, consectetur adipisicing elit. Quam culpa ad est debitis, dolor a quibusdam non perspiciatis fugiat odio rem, blanditiis facilis repudiandae. Sint ab suscipit reprehenderit a quidem! Lorem ipsum dolor, sit amet consectetur adipisicing elit. Quisquam repellendus adipisci voluptatum architecto nemo qui unde repellat sequi suscipit sint iure sed minima quis aspernatur sapiente error corporis, earum quas?',
        src: 'https://cdn.vuetifyjs.com/images/cards/house.jpg'
      },
      {
        title: 'Solar panel',
        text: '18/10/2019',
        content:
          "Aligarh Muslim University, the university I chose to pursue my bachelor's degree. It was not an easy decision, but somehow I managed to get in there. Electrical Engineering was never on my list, but when you are unable to get your dream branch you have to be satisfied with what your faith is. So, here I am studying Electrical Engineering at AMU. First month, away from home was like jumping straight into hell. I have never met so many new people in such a short span of time. But still I managed to make myself comfortable away from home. I kept myself busy with college work. One of the best platforms that I encountered at AMU was the AMU-OSS (Open source society of Aligarh Muslim University). There I met a lot of awesome seniors. They never treated me as their junior, rather they treated me as their brother. Though I was familiar with git and GitHub before joining college, here I came to know the real power of it. Version Control System was the real term and the power that I learnt there. GSOC and ROS, two terms that made my semester full of curiosity. And it let me gain an interest in web development and robotics . Along with this I improvised my Python skills by reading books such as Learn Python The Hard Way. MIT's course 6.00.1(Introduction to Computer Science and Programming in Python) was a great help. Later, I made my first Pull Request with the help of the AMU-OSS team. Apart from technical learning, I decided to join a sport which I never played and thus I joined the hockey club of my hostel. Playing hockey was not a cakewalk as I have never played it in my life. I practised daily and even managed to enter the club's team for the interhall tournament. I fought really hard with academics as it was not easy to manage academics and learning coding simultaneously. Well, the curriculum of AMU is easy from other universities so I was able to score decent marks. Final Exams got over, time for vacations and new plans . I decided to learn concepts of backend and Django. And a wait for the beginning of next semester……………..",
        src: 'https://cdn.vuetifyjs.com/images/cards/road.jpg'
      },
      {
        title: 'Induction',
        text: '12/11/2019',
        content:
          'Lorem ipsum dolor sit amet consectetur adipisicing elit. Beatae expedita exercitationem vitae qui fugit totam quam eos alias ullam obcaecati, nostrum nemo odio recusandae! Laboriosam ipsa nesciunt sunt neque recusandae. Lorem ipsum dolor sit amet, consectetur adipisicing elit. Quam culpa ad est debitis, dolor a quibusdam non perspiciatis fugiat odio rem, blanditiis facilis repudiandae. Sint ab suscipit reprehenderit a quidem! Lorem ipsum dolor, sit amet consectetur adipisicing elit. Quisquam repellendus adipisci voluptatum architecto nemo qui unde repellat sequi suscipit sint iure sed minima quis aspernatur sapiente error corporis, earum quas?',
        src: 'https://cdn.vuetifyjs.com/images/cards/plane.jpg'
      },
      {
        title: 'Internship',
        text: '07/03/2020',
        content:
          'Lorem ipsum dolor sit amet consectetur adipisicing elit. Beatae expedita exercitationem vitae qui fugit totam quam eos alias ullam obcaecati, nostrum nemo odio recusandae! Laboriosam ipsa nesciunt sunt neque recusandae. Lorem ipsum dolor sit amet, consectetur adipisicing elit. Quam culpa ad est debitis, dolor a quibusdam non perspiciatis fugiat odio rem, blanditiis facilis repudiandae. Sint ab suscipit reprehenderit a quidem! Lorem ipsum dolor, sit amet consectetur adipisicing elit. Quisquam repellendus adipisci voluptatum architecto nemo qui unde repellat sequi suscipit sint iure sed minima quis aspernatur sapiente error corporis, earum quas?',
        src: 'https://cdn.vuetifyjs.com/images/cards/plane.jpg'
      },
      {
        title: 'Induction',
        text: '12/11/2019',
        content:
          'Lorem ipsum dolor sit amet consectetur adipisicing elit. Beatae expedita exercitationem vitae qui fugit totam quam eos alias ullam obcaecati, nostrum nemo odio recusandae! Laboriosam ipsa nesciunt sunt neque recusandae. Lorem ipsum dolor sit amet, consectetur adipisicing elit. Quam culpa ad est debitis, dolor a quibusdam non perspiciatis fugiat odio rem, blanditiis facilis repudiandae. Sint ab suscipit reprehenderit a quidem! Lorem ipsum dolor, sit amet consectetur adipisicing elit. Quisquam repellendus adipisci voluptatum architecto nemo qui unde repellat sequi suscipit sint iure sed minima quis aspernatur sapiente error corporis, earum quas?',
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
