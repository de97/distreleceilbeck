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
            <p class="relproduct__name">
              {{ product.name }}
            </p>
            <ul class="relpoduct__list">
              <li class="relproduct__item">
                Stock {{ product.itemPositionOneBased }}
              </li>
              <li class="relproduct__item">
                {{ product.price.currency }} {{ product.price.formattedValue }}
              </li>
            </ul>
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
      settings: {
        arrows: true,
        dots: true,
        slidesToShow: 4,
        slidesToScroll: 4,
       
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
              dots: false
            }
          }

        ],
      },
    };
  },
};
</script>
