<template>
  <div id="app">
    <section>
    <VueSlickCarousel :arrows="true" :dots="true">
      <div>1</div>
      <div>2</div>
    </VueSlickCarousel>
    </section>
     <!-- <li v-for="product in products.carouselData" :key="product.code">
      {{product.name}}
    </li> -->
  </div>
  
</template>

<script>
import VueSlickCarousel from "vue-slick-carousel";
import "vue-slick-carousel/dist/vue-slick-carousel.css";
import "vue-slick-carousel/dist/vue-slick-carousel-theme.css";

import relProdData from "./data.json"

export default {
  name: "MyComponent",
  components: { VueSlickCarousel },
  products: relProdData,
};
</script>

<style>
body {
  margin: 5;
}
.arrows {
  color: red;
}
</style>
