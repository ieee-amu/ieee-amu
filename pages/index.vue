<template>
  <div>
    <v-carousel>
      <v-carousel-item v-for="(item, i) in items" :key="i" :src="item.src" />
    </v-carousel>
    <v-container>
      <v-row row wrap>
        <v-col sm12 lg8>
          <v-row row wrap>
            <v-container fluid>
              <v-row>
                <v-col cols="12">
                  <v-row
                    :align="alignment"
                    :justify="justify"
                    class="grey lighten-5"
                    style="height: 300px;"
                  >
                    <v-card class="ma-3 pa-6">
                      Lorem ipsum dolor sit amet consectetur adipisicing elit.
                      Minus saepe autem id, animi illum praesentium laboriosam
                      velit odit unde et atque vel fuga inventore dolor, nostrum
                      facere quaerat a mollitia.
                    </v-card>
                  </v-row>
                </v-col>
              </v-row>
            </v-container>
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
      ],
      alignmentsAvailable: ['start', 'center', 'end', 'baseline', 'stretch'],
      alignment: 'center',
      dense: false,
      justifyAvailable: [
        'start',
        'center',
        'end',
        'space-around',
        'space-between'
      ],
      justify: 'center'
    }
  }
}
</script>
