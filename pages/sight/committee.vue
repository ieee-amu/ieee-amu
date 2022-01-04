<template>
  <div>
    <div>
      <h2
        class="heading"
        align="center"
        style="margin-top: 20px; font-weight: bold; font-size: 50px"
      >
        Steering Commitee
      </h2>
      <v-container>
        <v-row v-for="members in sight_team" :key="members.id" justify="center">
          <v-col cols="12" md="7" lg="5" class="d-flex align-center">
            <div class="block text-center text-md-left">
              <h2 class="formbanner1-title font-weight-bold">
                {{ members.name }}
              </h2>
              <p class="mt-2 pt-2" style="font-weight: bold">
                {{ members.post }}
              </p>
              <p
                class="mt-2 pt-2"
                style="text-align: justify; word-wrap: break-word"
              >
                {{ members.description }}
              </p>
            </div>
          </v-col>
          <v-col cols="12" md="5" lg="6" class="ml-auto">
            <v-img id="pic" class="center" inherit :src="members.src" />
          </v-col>
        </v-row>
      </v-container>
    </div>
  </div>
</template>
<script>
export default {
  components: {},
  data() {
    return {
      sight_team: [],
      tab: null,
    }
  },
  created() {
    this.$fireStore
      .collection('sight_team')
      .get()
      .then((querySnapshot) => {
        querySnapshot.forEach((doc) => {
          const docObj = doc.data()
          docObj.id = doc.id
          this.sight_team.push(docObj)
        })
      })
  },
}
</script>
<style scoped>
@media (max-width: 1000px) {
  .formbanner1-title {
    align-content: center;
  }
  .block {
    margin-right: 10px;
  }
  .center {
    width: 60%;
    margin: auto;
    align-content: center;
    height: 80%;
  }
  #v-img {
    background-size: cover;
    align-content: center;
    padding-right: 100px;
  }
}
@media (min-width: 1000px) {
  .block {
    margin-left: 0px;
    margin-right: -250px;
  }

  .center {
    display: block;
    margin-top: 5rem;
    margin-left: 250px;
    margin-right: 0;
    width: 100%;
    height: 60%;
    width: 240px;
    background-size: cover;
    height: 240px;
  }
}

.image {
  width: 100%;
}
.formbanner1-title {
  font-size: 35px;
  line-height: 1;
  letter-spacing: -1px;
}
.back {
  background-size: cover;
  background-position: center center;
  background-repeat: no-repeat;
  width: 100%;
  background-blend-mode: hard-light;
  height: 53vh;
  opacity: 0.85;
  position: absolute;
}
#pic {
  margin-top: 40px;
  border-radius: 100%;
  background-size: cover;
}
</style>

