<template>
  <div>
    <v-carousel>
      <v-carousel-item v-for="(item, i) in items" :key="i" :src="item.src" />
    </v-carousel>
    <v-container>
      <v-row row wrap>
        <v-col sm12 lg8>
          <v-row row wrap>
            <div>
              Lorem ipsum dolor sit amet consectetur, adipisicing elit.
              Accusantium aspernatur ex asperiores illum maxime natus, vero
              <br />
              aliquid, nam aliquam adipisci architecto expedita blanditiis
              deserunt sed? Aperiam delectus quibusdam tenetur excepturi?
            </div>
          </v-row>
        </v-col>
      </v-row>
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
