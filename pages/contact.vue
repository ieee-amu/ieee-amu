<template>
  <v-container mt-4>
    <v-row justify="center">
      <v-col cols="12" sm="6" md="4">
        <h1 class="text-left display-3 font-weight-regular">Reach out to us</h1>
        <v-divider class="mt-4" />
      </v-col>
      <v-col cols="12" sm="2" md="2">
        <span></span>
      </v-col>
    </v-row>
    <v-form>
      <v-container class="mt-10">
        <v-row justify="center">
          <v-col cols="12" sm="4" md="3">
            <v-text-field v-model="name" label="Full name"></v-text-field>
          </v-col>

          <v-col cols="12" sm="4" md="3">
            <v-text-field v-model="email" label="Email address"></v-text-field>
          </v-col>
        </v-row>
        <v-row justify="center">
          <v-col xs="12" sm="8" md="6">
            <v-textarea
              v-model="message"
              outlined
              label="Type a message or query"
            ></v-textarea>
          </v-col>
        </v-row>
      </v-container>
    </v-form>
    <div class="text-center">
      <v-btn @click="submit" large color="dark">
        Send &nbsp; <v-icon>mdi-send</v-icon>
      </v-btn>
    </div>
    <!-- eslint-disable-next-line vue/require-component-is -->
    <component :is="componentName" v-bind="{ show: true }"></component>
  </v-container>
</template>

<script>
import DialogBox from '@/components/DialogBox'

export default {
  data() {
    return {
      componentName: '',
      sendSuccess: false,
      name: '',
      email: '',
      message: ''
    }
  },

  computed: {
    formOk() {
      return !!(this.name && this.email && this.message)
    }
  },

  methods: {
    submit() {
      if (this.formOk) {
        this.$fireStore
          .collection('messages')
          .add({
            visitor: {
              email: this.email,
              fullName: this.name
            },
            message: this.message,
            didAdminRespond: false,
            date: new Date().toDateString()
          })
          .then(() => {
            // Render dialog-box component on success
            this.componentName = DialogBox
          })
      }
    }
  }
}
</script>
