<template>
  <carousel
    :navigation="true"
    :pagination="true"
    :startAutoPlay="true"
    :timeout="10000"
    v-slot="{ currentSlide }"
  >
    <slider v-for="(slide, index) in sliders" :key="index">
      <div v-show="currentSlide === index + 1">
        <img :src="slide" alt="" />
      </div>
    </slider>
  </carousel>
</template>

<script>
import { reactive } from "@vue/reactivity";
import Carousel from "./components/Carousel.vue";
import Slider from "./components/Slider.vue";
export default {
  name: "App",
  components: {
    Carousel,
    Slider,
  },
  setup() {
    const sliders = reactive([
      "../assets/bg-1.jpg",
      "../assets/bg-2.jpg",
      "../assets/bg-3.jpg",
    ]);
    return { sliders };
  },
};
</script>
<style lang="scss">
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
</style>
