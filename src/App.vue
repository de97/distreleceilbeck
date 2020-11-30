<template>
  <div id="app">
    <container>
    <h1>Related Products</h1>
      <VueSlickCarousel :dots="true" :slidesToShow=4 :slidesToScroll=4>
        <div
          class="relproduct__id"
          v-for="product in products.carouselData"
          :key="product.code"
        >
          <div class="relproduct__content">
            <!-- <img class=relproduct__img src="https://www.distrelec.biz/Web/WebShopImages/landscape_medium/ho/to/SO-16W-Photo.jpg"> -->
            <img class=relproduct__img src= ${product.productImageUrl}>
            <p class="relproduct__name">
              {{ product.name }}
            </p>
            <ul class="relpoduct__list">
              <li class="relproduct__item">Stock {{product.itemPositionOneBased}}</li>
              <li class="relproduct__item">{{product.price.currency}} {{product.price.formattedValue}}</li>
            </ul>
            <button class="relproduct__button">Buy now</button>
          </div>
        </div>
      </VueSlickCarousel>
    </container>
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