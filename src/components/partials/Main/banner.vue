<template>
  <div class="container" id="1">
    <div class="wrapperr">
      <swiper ref="mySwiper" :options="swiperOptions">
        <swiper-slide v-for="(slide, index) in slides" :key="index">
          <div class="image-slider__slide">
            <div class="image-slider__image">
              <img :src="require(`../../../assets/img/${slide}`)" alt=""/>
            </div>
          </div>
        </swiper-slide>
        <template #pagination>
          <div class="swiper-pagination"></div>
        </template>
        <template #prev-button>
          <div class="swiper-button-prev"></div>
        </template>
        <template #next-button>
          <div class="swiper-button-next"></div>
        </template>
      </swiper>
    </div>
  </div>
</template>

<script>
import { ref } from "vue";
import SwiperClass, { Pagination } from "swiper";
import { Swiper, SwiperSlide } from "vue-awesome-swiper";
import "swiper/css";
import "swiper/css/pagination";

export default {
  components: {
    Swiper,
    SwiperSlide,
  },
  setup() {
    const slides = ref(["1448067.webp", "8583.webp", "8589.webp"]);

    const swiperOptions = ref({
      navigation: {
        nextEl: ".swiper-button-next",
        prevEl: ".swiper-button-prev",
      },
      pagination: {
        el: ".swiper-pagination",
        clickable: true,
      },
    });

    return {
      slides,
      swiperOptions,
    };
  },
};
</script>

<style lang="scss">
.container {
  width: 780px;
  margin: 40px auto 0 auto;

}

.image-slider__image img {
  height: 439px;
}

@media screen and (max-width: 1100px) {
  .container {
    width: 78%;
  }

  .image-slider__image img {
    height: 43.1vw;
  }
}
</style>
