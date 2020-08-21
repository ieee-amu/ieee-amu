<template>
  <section :style="{ 'margin-top': gap + '%;' }"></section>
</template>

<script>
export default {
  props: {
    gap: {
      type: String,
      default: '5',
    },
  },
}
</script>

<style scoped>
section {
  margin-top: 5%;
  margin-bottom: 5%;
}
</style>
