<template>
  <v-container>
    <v-row justify="center">
      <v-tabs centered class="elevation-2">
        <v-tabs-slider></v-tabs-slider>
        <v-tab href="#unresponded"> UNRESPONDED </v-tab>
        <v-tab href="#responded"> RESPONDED </v-tab>

        <v-tab-item value="unresponded">
          <ContactMessages :messages="unrespondedMessages" />
        </v-tab-item>
        <v-tab-item value="responded">
          <ContactMessages :messages="respondedMessages" />
        </v-tab-item>
      </v-tabs>
    </v-row>
  </v-container>
</template>

<script>
// Not implementing pagination in Firestore queries as it would be premature
// optimization given the traffic this site is gonna receive.
import ContactMessages from './contactMessages'

export default {
  components: { ContactMessages },
  data() {
    return {
      respondedMessages: [],
      unrespondedMessages: [],
    }
  },
  created() {
    this.$fireStore
      .collection('messages')
      .get()
      .then((querySnapshot) => {
        querySnapshot.forEach((doc) => {
          const data = doc.data()
          data.id = doc.id // Add doc id field for v-for key
          if (data.didAdminRespond) {
            this.respondedMessages.push(data)
          } else {
            this.unrespondedMessages.push(data)
          }
        })
      })
  },
  beforeMount() {
    if (!this.$fireAuth.currentUser) {
      return this.$router.push({ path: '/administrator/login' })
    }
  },
}
</script>
