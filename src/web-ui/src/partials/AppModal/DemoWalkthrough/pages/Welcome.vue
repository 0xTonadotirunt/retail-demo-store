<template>
  <DemoWalkthroughPageLayout class="page-container text-center" :showNav="false">
    <h1 class="heading mb-4">About BestiesShopHub!</h1>
    <p class="text mb-5">
      We are an online platform selling tech goods is a digital marketplace dedicated to the sale and distribution of a wide range of technology-related products and gadgets. We provide a convenient and accessible way for consumers and businesses to purchase items such as smartphones, laptops, tablets, gaming consoles, accessories, software, and various other electronic devices. We often feature product listings, detailed specifications, user reviews, and secure payment options. 
    </p>
    <div class="d-flex flex-column flex-sm-row-reverse justify-content-center">
      <!-- <button class="take-tour btn btn-primary mb-3 mb-sm-0" @click="nextTourPage">Take Tour</button> -->
      <button class="skip btn btn-outline-primary mr-sm-3" @click="endTour">Continue</button>
    </div>
  </DemoWalkthroughPageLayout>
</template>

<script>
import { mapActions } from 'vuex';

import DemoWalkthroughPageLayout from '../DemoWalkthroughPageLayout.vue';

import { APP_MODAL_ID } from '../../config';

export default {
  name: 'DemoWalkthroughWelcomePage',
  methods: {
    ...mapActions(['nextTourPage']),
    endTour() {
      // eslint-disable-next-line no-undef
      $(`#${APP_MODAL_ID}`).modal('hide');
    },
  },
  components: {
    DemoWalkthroughPageLayout,
  },
};
</script>

<style scoped>
.page-container {
  font-size: 1.25rem;
}

.heading {
  margin-top: 20%;
  font-size: 2rem;
}

.skip,
.take-tour {
  font: inherit;
  color: inherit;
}

.skip {
  border-color: var(--blue-500);
}

.skip:hover,
.skip:focus {
  background-color: var(--blue-600);
  border-color: var(--blue-600);
}

.take-tour {
  display: block;
  background-color: var(--blue-500);
  border-color: var(--blue-500);
}

.take-tour:hover,
.take-tour:focus {
  background-color: var(--blue-600);
  border-color: var(--blue-600);
}

@media (min-width: 576px) {
  .skip,
  .take-tour {
    width: 200px;
  }
}
</style>
