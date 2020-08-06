<template>
  <v-dialog v-model="showDialog" max-width="290">
    <v-card>
      <v-card-title class="headline">
        Message sent
      </v-card-title>

      <v-card-text>
        Your message was delivered! Keep an eye at your inbox for a response!
      </v-card-text>

      <v-card-actions>
        <v-spacer></v-spacer>

        <v-btn @click="closeDialog" text>OK</v-btn>
      </v-card-actions>
    </v-card>
  </v-dialog>
</template>

<script>
export default {
  props: {
    show: {
      type: Boolean,
      required: true
    }
  },

  data() {
    return {
      showDialog: this.show
    }
  },
  methods: {
    closeDialog() {
      this.showDialog = false
    }
  }
}
</script>
