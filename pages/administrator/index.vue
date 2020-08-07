<template>
  <div>
    Logged in as admin.
    <!-- Replace this later with a dashboard -->
  </div>
</template>

<script>
export default {
  beforeMount() {
    if (!this.$fireAuth.currentUser) {
      return this.$router.push({ path: '/administrator/login' })
    }
  }
}
</script>
