<template>
  <div id="app">
    <section>
      <VueSlickCarousel :dots="true" :slidesToShow=3>
        <div
          class="relproduct"
          v-for="product in products.carouselData"
          :key="product.code"
        >
          <div class="relproduct__content">
            <img src="product.url">
            <p class="relproduct__name">
              {{ product.name }}
            </p>
            <ul class="relpoduct__list">
              <li class="relproduct__item">Stock: 3</li>
              <li class="relproduct__item">Euro 940</li>
            </ul>
            <button class="relproduct__button">Buy now</button>
          </div>
        </div>
      </VueSlickCarousel>
    </section>
  </div>
</template>

<script>
import VueSlickCarousel from "vue-slick-carousel";
import "vue-slick-carousel/dist/vue-slick-carousel.css";
import "vue-slick-carousel/dist/vue-slick-carousel-theme.css";
import "./styles/style.css";

import relProdData from "./data.json";

export default {
  name: "MyComponent",
  components: { VueSlickCarousel },
  data() {
    return {
      products: relProdData,
    };
  },
};
</script>


//<span class="relproduct__img"> {{ product.url }}</span>