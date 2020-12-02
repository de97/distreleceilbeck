<!--- Important! please intsall the vue-slick-carousel pacakge for this project to run: https://www.npmjs.com/package/vue-slick-carousel --->
<template>
  <div id="app">
    <div class="container">
      <h1>Related Products</h1>
      <VueSlickCarousel v-bind="settings">
        <div
          class="relproduct__id"
          v-for="product in products.carouselData"
          :key="product.code"
        >
          <div class="relproduct__content">
            
            <img
              class="relproduct__image"
              style="max-width: 20%"
              :src="product.productImageUrl"
            />
            <div class="relproduct__container">
              <p class="relproduct__name">
                {{ product.name }}
              </p>
            </div>
            <li class="relproduct__item">
              Stock: {{ product.itemPositionOneBased }}
            </li>
            <li class="relproduct__item">
              <span class="bold__text"
                >{{ product.price.currency }}: £{{
                  product.price.formattedValue
                }}</span
              >
            </li>
            <a class="relproduct_link" :href="product.url">Buy Now</a>
          </div>
        </div>
      </VueSlickCarousel>
    </div>
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
      //Settings for View-slick-carousel
      settings: {
        arrows: true,
        dots: true,
        slidesToShow: 4,
        slidesToScroll: 4,
        autoplay: true,
        autoplaySpeed: 5000,
        pauseOnDotsHover: true,
        pauseOnFocus: true,
        pauseOnHover: true,
        responsive: [
          {
            breakpoint: 1000,
            settings: {
              slidesToShow: 3,
              slidesToScroll: 3,
            },
          },
          {
            breakpoint: 600,
            settings: {
              slidesToShow: 2,
              slidesToScroll: 2,
            },
          },
          {
            breakpoint: 400,
            settings: {
              slidesToShow: 1,
              slidesToScroll: 1,
              dots: false,
            },
          },
        ],
      },
    };
  },
};
</script>
