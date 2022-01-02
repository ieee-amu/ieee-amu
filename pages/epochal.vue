<template>
  <div class="formbanner1-component">
    <v-container>
      <v-row justify="center">
        <v-col cols="12" md="10" lg="6" class="d-flex align-center">
          <div class="text-center text-md-left">
            <h2 class="formbanner1-title font-weight-bold">About Epochal</h2>
            <p class="mt-2 pt-2" style="text-align: justify">
              Epochal provides a platform for young aspiring engineers to come
              together and be a part of a collaborative space; a society
              (sub-section within SIGHT?) meant for learning and growing
              together in the field of research and engineering choosing from
              among a variety of (sub-)societies. The idea is to foster younger
              minds of ZHCET into identifying their niche, and adapting to a
              research environment which aligns to their career goals and
              interests. So, we as the research section of the student branch
              aim to create collaboration opportunities and bridge the gap
              between hands-on knowledge and theoretical knowledge by means of
              practical exposure.
            </p>
          </div>
        </v-col>
        <v-col cols="12" md="3" lg="5" class="ml-auto">
          <v-card class="mx-auto" color="#26c6da">
            <v-card-title style="font-weight: bold">
              Join Us Today
            </v-card-title>
            <iframe
              src="https://docs.google.com/forms/d/e/1FAIpQLSef92WstGozBDCRfSh_2iiJmsgqEvHRxYqAPE7A3XUnt4hfBg/viewform?embedded=true"
              height="1000"
              style="width: 100%; height: 70vh"
              frameborder="0"
              allowfullscreen=""
              title="Embedded form"
              >Loading…</iframe
            >
          </v-card>
        </v-col>
      </v-row>
    </v-container>
    <v-row class="mt-13" justify="center">
      <v-col cols="12" md="6" lg="4">
        <v-card
          outlined
          elevation="0"
          class="pricing-card overflow-hidden mb-15"
        >
          <v-card-text class="text-center pa-15">
            <h5 class="font-weight-regular font-18">Regular Plan</h5>
            <div>
              <sup>$</sup>
              <span class="price-text">39</span>
              <h6 class="font-14 text-uppercase font-weight-regular">Yearly</h6>
            </div>
            <p class="mt-16 pt-4">
              The Master license allows you to customize, store and even host
              your website using your platform
            </p>
          </v-card-text>
          <v-btn
            block
            large
            depressed
            color="info"
            class="text-uppercase rounded-t-0"
          >
            Choose Plan
          </v-btn>
        </v-card>
      </v-col>
      <v-col cols="12" md="6" lg="4">
        <v-card
          outlined
          elevation="0"
          class="pricing-card overflow-hidden mb-15"
        >
          <v-card-text class="text-center pa-15">
            <h5 class="font-weight-regular font-18">Master Plan</h5>
            <div>
              <sup>$</sup>
              <span class="price-text">49</span>
              <h6 class="font-14 text-uppercase font-weight-regular">Yearly</h6>
            </div>
            <p class="mt-16 pt-4">
              The Master license allows you to customize, store and even host
              your website using your platform
            </p>
          </v-card-text>
          <v-btn
            block
            large
            depressed
            color="error"
            class="text-uppercase rounded-t-0"
          >
            Choose Plan
          </v-btn>
        </v-card>
      </v-col>
      <v-col cols="12" md="6" lg="4">
        <v-card
          outlined
          elevation="0"
          class="pricing-card overflow-hidden mb-15"
        >
          <v-card-text class="text-center pa-15">
            <h5 class="font-weight-regular font-18">Premium Plan</h5>
            <div>
              <sup>$</sup>
              <span class="price-text">69</span>
              <h6 class="font-14 text-uppercase font-weight-regular">Yearly</h6>
            </div>
            <p class="mt-16 pt-4">
              The Master license allows you to customize, store and even host
              your website using your platform
            </p>
          </v-card-text>
          <v-btn
            block
            large
            depressed
            color="info"
            class="text-uppercase rounded-t-0"
          >
            Choose Plan
          </v-btn>
        </v-card>
      </v-col>
    </v-row>
  </div>
</template>
<style scoped>
.formbanner1-component {
  background-size: cover;
  background-position: center center;
  background-repeat: no-repeat;
  width: 100%;
  margin: 0;
  background-blend-mode: hard-light;
  max-height: 700px;
}
.formbanner1-title {
  font-size: 48px;
  line-height: 1;
  letter-spacing: -1px;
  margin: 20px 0 15px;
}
</style>
