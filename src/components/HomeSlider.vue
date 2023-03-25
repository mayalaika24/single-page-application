<template>
  <div id="homeSlider">
    <Carousel
      :perPage="1"
      :autoplay="true"
      :loop="true"
      :paginationEnabled="false"
    >
      <Slide
        ref="slider"
        class="slider-container m-0 p-0"
        v-for="(item, index) in data"
        :key="index"
      >
        <div
          class="img-container"
          v-bind:style="{ backgroundImage: 'url(' + item + ')' }"
        ></div>
      </Slide>
    </Carousel>
  </div>
</template>
<script>
import { Carousel, Slide } from "vue-carousel";
import makeup1 from "../assets/homeSlider/makeup-1.jpg";
import makeup2 from "../assets/homeSlider/makeup-2.jpg";
import makeup3 from "../assets/homeSlider/makeup-3.jpg";
import makeup5 from "../assets/homeSlider/makeup-5.jpg";
export default {
  components: { Carousel, Slide },
  data() {
    return {
      data: [makeup1, makeup2, makeup3, makeup5],
    };
  },
  mounted() {},
};
</script>
<style>
.slider-container {
  height: 100vh;
  width: 100vw;
  overflow-x: hidden;
}
.img-container {
  height: 100%;
  width: 100%;
  background-size: cover;
}
</style>
