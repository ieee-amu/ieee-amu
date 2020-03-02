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
                      <p>
                        Bacon ipsum dolor amet shoulder alcatra chislic ball tip
                        kielbasa ground round kevin tongue flank pork. Pork
                        belly flank rump jowl capicola buffalo meatloaf meatball
                        fatback pastrami alcatra ham hock frankfurter. Alcatra
                        short ribs bacon spare ribs brisket fatback. Spare ribs
                        beef shank sirloin, meatloaf strip steak jerky alcatra
                        ham hock. Venison andouille bresaola, picanha kevin
                        tenderloin turducken alcatra pork chop salami.
                      </p>

                      <p>
                        kielbasa porchetta shoulder ham hock, tail ribeye
                        prosciutto pork loin buffalo meatloaf drumstick
                        pancetta. Landjaeger shoulder brisket tenderloin ground
                        round. Turkey andouille strip steak bacon pork loin
                        meatball tail short ribs. Fatback pork kevin, alcatra
                        pork loin chuck sirloin filet mignon. Fatback t-bone
                        landjaeger, kielbasa strip steak tri-tip capicola
                        sirloin ribeye turkey burgdoggen tail pork chop biltong.
                      </p>
                      <p>
                        Pork chop strip steak salami pork belly rump leberkas.
                        Short loin porchetta landjaeger jowl salami ribeye
                        sausage drumstick shank. Pork loin corned beef spare
                        ribs beef ribs, brisket capicola pork chop pastrami rump
                        pig burgdoggen picanha fatback tail. Landjaeger bresaola
                        pork loin picanha jerky. Short loin ham kevin pork
                        salami pastrami leberkas drumstick turducken capicola
                        short ribs andouille.
                      </p>
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
