<template>
  <v-container mt-4>
    <v-row style="display: flex; justify-content: center">
      <v-col class="back order-last order-md-first" cols="12" md="6"
        ><v-container style="color: white">
          <v-row class="pb-0">
            <v-col class="mx-auto pb-0" cols="8">
              <v-row>
                <v-col style="padding-left: 0" cols="2">
                  <v-icon color="white" size="32">mdi-map-marker-radius</v-icon>
                </v-col>
                <v-col cols="8">Address</v-col>
              </v-row>
            </v-col>
            <v-col class="mx-auto py-0" cols="8">
              <v-row class="py-0">
                <v-col class="pt-0" cols="2"></v-col>
                <v-col class="pt-0" cols="8">
                  Electrical Engineering Department ZHCET, AMU
                </v-col>
              </v-row>
            </v-col>
          </v-row>
          <v-row>
            <v-col class="mx-auto pb-0" cols="8">
              <v-row>
                <v-col style="padding-left: 0" cols="2"
                  ><v-icon color="white" size="32"
                    >mdi-phone-forward</v-icon
                  ></v-col
                >
                <v-col cols="6">Let's Talk</v-col>
              </v-row>
            </v-col>
            <v-col class="mx-auto py-0" cols="8">
              <v-row>
                <v-col class="pt-0" cols="2"></v-col>
                <v-col class="pt-0" cols="8"> +91-9412690509 </v-col>
              </v-row>
            </v-col>
          </v-row>
          <v-row>
            <v-col class="mx-auto pb-0" cols="8">
              <v-row>
                <v-col style="padding-left: 0" cols="2"
                  ><v-icon color="white" size="32">mdi-gmail</v-icon></v-col
                >
                <v-col cols="8">Support</v-col>
              </v-row>
            </v-col>
            <v-col class="mx-auto py-0" cols="8">
              <v-row>
                <v-col class="pt-0" cols="2"></v-col>
                <v-col class="pt-0" cols="8"> ieeeamu.zhcet@gmail.com </v-col>
              </v-row>
            </v-col>
          </v-row>
        </v-container>
      </v-col>
      <v-col class="order-md-last order-first" cols="12" md="6">
        <v-row
          ><v-col class="mx-auto" cols="10" md="12">
            <h1 class="text-center display-3 font-weight-regular">
              Contact us
            </h1>
          </v-col></v-row
        >
        <v-form>
          <v-container class="mt-3">
            <v-row justify="center">
              <v-col cols="8" md="12">
                <v-text-field
                  v-model="name"
                  class="input"
                  label="Full name"
                ></v-text-field>
              </v-col>

              <v-col cols="8" md="12">
                <v-text-field
                  v-model="email"
                  class="input"
                  label="Email address"
                ></v-text-field>
              </v-col>
            </v-row>
            <v-row justify="center">
              <v-col cols="8" md="10" class="input">
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
          <v-btn large color="dark" @click="submit">
            Send &nbsp; <v-icon>mdi-send</v-icon>
          </v-btn>
        </div>
        <!-- eslint-disable-next-line vue/require-component-is -->
        <component :is="componentName" v-bind="{ show: true }"></component
      ></v-col>
    </v-row>
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
      message: '',
    }
  },

  computed: {
    formOk() {
      return !!(this.name && this.email && this.message)
    },
  },

  methods: {
    submit() {
      if (this.formOk) {
        this.$fireStore
          .collection('messages')
          .add({
            visitor: {
              email: this.email,
              fullName: this.name,
            },
            message: this.message,
            didAdminRespond: false,
            date: new Date().toDateString(),
          })
          .then(() => {
            // Render dialog-box component on success
            this.componentName = DialogBox
          })
      }
    },
  },
}
</script>
<style>
h1 {
  width: 70%;
  margin: auto;
  font-size: 0.6rem;
  padding-bottom: 2rem;
  border-bottom: 1px solid lightgray;
}
.back {
  background-image: url(https://upload.wikimedia.org/wikipedia/commons/8/86/Victoria_Gate_AMU_Aligarh_-_panoramio.jpg);
  background-position: center;
  padding: 0;
  background-size: cover;
  box-shadow: inset 0 0 100px black;
  background-blend-mode: multiply;
  background-color: rgb(55 55 55 / 84%);
  display: flex;
  justify-content: center;
  align-items: center;
}
.input {
  width: 70%;
  margin: auto;
}
@media (max-width: 480px) {
  h1 {
    text-align: left !important;
    font-size: 2.5rem !important;
  }
  .input {
    width: 100%;
  }
}
</style>
