<template>
  <v-container>
    <v-row justify="center">
      <v-tabs centered class="elevation-2">
        <v-tabs-slider></v-tabs-slider>
        <v-tab href="#unresponded">
          UNRESPONDED
        </v-tab>
        <v-tab href="#responded">
          RESPONDED
        </v-tab>

        <v-tab-item value="unresponded">
          <v-list>
            <v-list-group v-for="msg in messages" :key="msg.id" no-action>
              <template v-slot:activator>
                <v-list-item-content>
                  <v-list-item-title>
                    <strong>{{ msg.visitor.fullName }}</strong>
                    ({{ msg.visitor.email }})
                  </v-list-item-title>
                </v-list-item-content>
              </template>
              <v-list-item>
                <v-list-item-content>
                  <v-list-item-subtitle
                    v-text="msg.message"
                  ></v-list-item-subtitle>
                </v-list-item-content>
              </v-list-item>
            </v-list-group>
          </v-list>
        </v-tab-item>
        <v-tab-item value="responded">
          All messages responded to, go here.
        </v-tab-item>
      </v-tabs>
    </v-row>
  </v-container>
</template>

<script>
// Not implementing pagination in Firestore queries as it would be premature
// optimization given the traffic this site is gonna receive.

export default {
  data() {
    return {
      messages: [],
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
          this.messages.push(data)
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
