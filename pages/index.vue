<template>
  <div>
    <v-carousel>
      <v-carousel-item v-for="(item, i) in items" :key="i" :src="item.src" />
    </v-carousel>
    <v-container>
      <v-layout row wrap>
        <v-flex sm12 lg8>
          <v-layout row wrap>
            <div>
              Lorem ipsum dolor sit amet consectetur, adipisicing elit.
              Accusantium aspernatur ex asperiores illum maxime natus, vero
              <br />
              aliquid, nam aliquam adipisci architecto expedita blanditiis
              deserunt sed? Aperiam delectus quibusdam tenetur excepturi?
            </div>
          </v-layout>
        </v-flex>
      </v-layout>
    </v-container>
  </div>
</template>

<script>
export default {
  data() {
    return {
      items: [
        {
          src: 'https://cdn.vuetifyjs.com/images/carousel/squirrel.jpg'
        },
        {
          src: 'https://cdn.vuetifyjs.com/images/carousel/sky.jpg'
        },
        {
          src: 'https://cdn.vuetifyjs.com/images/carousel/bird.jpg'
        },
        {
          src: 'https://cdn.vuetifyjs.com/images/carousel/planet.jpg'
        }
      ]
    }
  }
}
</script>
