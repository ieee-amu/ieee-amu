<template>
  <v-row align="center" justify="center" class="mt-10">
    <v-col cols="12" sm="8" md="4">
      <v-card class="elevation-12">
        <v-toolbar color="dark" dark flat>
          <v-toolbar-title>Admin Login</v-toolbar-title>
          <v-spacer></v-spacer>
        </v-toolbar>
        <v-card-text>
          <v-form>
            <v-text-field
              v-model="email"
              label="Email"
              prepend-icon="mdi-account"
              type="text"
            ></v-text-field>

            <v-text-field
              v-model="password"
              label="Password"
              prepend-icon="mdi-lock"
              type="password"
            ></v-text-field>
          </v-form>
        </v-card-text>
        <v-card-actions>
          <v-spacer></v-spacer>
          <v-btn @click="login" color="primary">Login</v-btn>
        </v-card-actions>
      </v-card>
    </v-col>
  </v-row>
</template>

<script>
export default {
  data() {
    return {
      email: '',
      password: ''
    }
  },
  methods: {
    login() {
      this.$fireAuth
        .signInWithEmailAndPassword(this.email, this.password)
        .then((user) => {
          this.$router.push({ path: '/administrator' })
        })
        // eslint-disable-next-line handle-callback-err
        .catch((err) => {
          this.$router.push('/administrator/login')
        })
    }
  }
}
</script>
