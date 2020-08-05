<template>
  <v-container mt-4>
    <v-row justify="space-around">
      <v-col cols="12">
        <h1 class="text-left display-3">Reach out</h1>
      </v-col>
    </v-row>
    <v-form>
      <v-container class="mt-10">
        <v-row justify="center">
          <v-col cols="12" sm="4" md="3">
            <v-text-field label="Full name"></v-text-field>
          </v-col>

          <v-col cols="12" sm="4" md="3">
            <v-text-field label="Email address"></v-text-field>
          </v-col>
        </v-row>
        <v-row justify="center">
          <v-col xs="12" sm="8" md="6">
            <v-textarea outlined label="Type a message or query"></v-textarea>
          </v-col>
        </v-row>
      </v-container>
    </v-form>
  </v-container>
</template>
