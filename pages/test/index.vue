<template>
  <div class="swiper" data-swiper="swiper-box">
    <div class="swiper-wrapper" ref="swiper_active">
      <div class="swiper-slide" style="height: 200px; background-color: red">
        Slide 1
      </div>
      <div class="swiper-slide" style="height: 400px; background-color: yellow">
        Slide 2
      </div>
      <div class="swiper-slide" style="height: 400px; background-color: blue">
        Slide 3
      </div>
    </div>
  </div>
</template>
<script>
import Swiper from "swiper";
import "swiper/swiper.scss";
export default {
  data() {
    return {
      swiper: null,
    };
  },
  mounted() {
    this.swiper = new Swiper('[data-swiper="swiper-box"]', {
      slidesPerView: 1,
      spaceBetween: 18,
      effect: "slide",
      speed: 300,
      resizeReInit: true,
      allowTouchMove: true,
      autoHeight: true,
      initialSlide: 0,
      on: {
        slideChange: () => {
          const activeSlide = this.swiper?.slides?.[this.swiper.activeIndex];
          const activeSlideHeight = activeSlide?.offsetHeight;
          console.log(activeSlideHeight);
          //   setTimeout(() => {
          //     this.$refs.swiper_active.style.height = `${activeSlideHeight}px`;
          //   }, 2500);
        },
      },
    });
  },
};
</script>