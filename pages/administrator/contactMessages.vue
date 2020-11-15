<template>
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
          <v-list-item-subtitle v-text="msg.message"></v-list-item-subtitle>
        </v-list-item-content>
      </v-list-item>
    </v-list-group>
  </v-list>
</template>

<script>
// Not implementing pagination in Firestore queries as it would be premature
// optimization given the traffic this site is gonna receive.

export default {
  name: 'ContactMessages',
  props: {
    messages: { type: Array, required: true },
  },
}
</script>
