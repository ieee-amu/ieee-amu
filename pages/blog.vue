<template>
  <v-container fluid>
    <v-row justify="center">
      <v-col cols="12" sm="10" md="8" lg="6">
        <v-card class="teal white--text">
          <div
            class="text-center headline pt-4 pb-4"
            style="font-family: 'Hammersmith One', sans-serif !important"
          >
            Reports
          </div>
        </v-card>
      </v-col>
    </v-row>
    <PageLoader v-show="!posts.length" />
    <v-row justify="center">
      <v-col
        v-for="post in posts"
        :key="post.id"
        cols="12"
        :style="{ order: -post.order }"
      >
        <v-card id="blog" class="mx-auto">
          <v-img
            :src="post.src"
            class="white--text align-end"
            gradient="to bottom, rgba(0,0,0,.1), rgba(0,0,0,.5)"
            height="400px"
            lazy-src="https://placeimg.com/800/400/tech/grayscale?t=1585342692664"
          >
            <template v-slot:placeholder>
              <v-row class="fill-height ma-0">
                <v-progress-linear
                  indeterminate
                  color="blue"
                ></v-progress-linear>
              </v-row>
            </template>
            <div
              class="justify-blog"
              style="font-family: 'Hammersmith One', sans-serif !important"
            >
              {{ post.title }}
            </div>
          </v-img>
          <v-card-text v-text="post.date"></v-card-text>
          <v-row justify="center">
            <v-dialog width="600px">
              <v-spacer />
              <template v-slot:activator="{ on }">
                <v-btn id="know-more" v-on="on">Know more</v-btn>
              </template>
              <v-card>
                <div id="dailog-title" class="grey lighten-2">
                  {{ post.title }}
                </div>
                <v-card-text class="body-1 font-weight-regular">
                  {{ post.content }}
                </v-card-text>
                <v-divider></v-divider>
                <v-card-actions>
                  <v-spacer></v-spacer>
                  <v-btn
                    :href="post.link"
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
import PageLoader from '@/components/PageLoader.vue'
export default {
  components: {
    PageLoader,
  },
  data() {
    return {
      posts: [],
    }
  },
  created() {
    this.$fireStore
      .collection('posts')
      .get()
      .then((querySnapshot) => {
        querySnapshot.forEach((doc) => {
          const docObj = doc.data()
          docObj.id = doc.id
          this.posts.push(docObj)
        })
      })
  },
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
#dailog-title {
  text-align: center;
  text-justify: inter-word;
  font-size: 20px;
  font-weight: 550;
  margin-bottom: 10px;
  padding-left: 2px;
  padding-top: 10px;
  padding-bottom: 10px;
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
