<template>
  <div id="makeup-section">
    <div class="section-title">Makeup section</div>
    <Carousel
      ref="slider"
      :paginationEnabled="true"
      :paginationActiveColor="paginationColor"
      :perPageCustom="[[900, 3], [700, 2] , [100, 1]]"
    >
      <Slide ref="slider" v-for="(item, index) in data" :key="index">
        <b-card
          :title="item.title"
          :img-src="item.img"
          img-alt="Image"
          img-top
          tag="article"
        >
          <b-card-text>
            {{ item.description }}
          </b-card-text>
        </b-card>
      </Slide>
    </Carousel>
  </div>
</template>

<script>
import { Carousel, Slide } from "vue-carousel";
import blush from "../assets/makeupSection/blush.jpg";
import blush2 from "../assets/makeupSection/blush2.jpg";
import blushTool from "../assets/makeupSection/blushTool.jpg";
import concealer from "../assets/makeupSection/concealer.jpg";
import eyeliner from "../assets/makeupSection/eyeliner.jpg";
import eyeliner2 from "../assets/makeupSection/eyeliner2.jpg";
import eyeshadow from "../assets/makeupSection/eyeshadow.jpg";
import mascara from "../assets/makeupSection/mascara.jpg";
import rouge from "../assets/makeupSection/rouge.jpg";
export default {
  name: "MyComponent",
  components: { Carousel, Slide },
  data() {
    return {
      paginationColor: "pink",
      perPage: 3,
      data: [
        {
          img: blush,
          title: "Light Blusher",
          description:
            "Lorem ipsum dolor sit amet, consectetuer adipiscing elit. Aenean commodo ligula eget dolor. Aenean massa. Cum sociis natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus. Donec quam felis, ultricies nec, pellentesque eu, pretium quis, sem. Nulla consequat massa quis enim.",
        },
        {
          img: blush2,
          title: "Red Blusher",
          description:
            "Lorem ipsum dolor sit amet, consectetuer adipiscing elit. Aenean commodo ligula eget dolor. Aenean massa. Cum sociis natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus. Donec quam felis, ultricies nec, pellentesque eu, pretium quis, sem. Nulla consequat massa quis enim.",
        },
        {
          img: blushTool,
          title: "Blush Tool ",
          description:
            "Lorem ipsum dolor sit amet, consectetuer adipiscing elit. Aenean commodo ligula eget dolor. Aenean massa. Cum sociis natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus. Donec quam felis, ultricies nec, pellentesque eu, pretium quis, sem. Nulla consequat massa quis enim.",
        },
        {
          img: concealer,
          title: "Concealer",
          description:
            "Lorem ipsum dolor sit amet, consectetuer adipiscing elit. Aenean commodo ligula eget dolor. Aenean massa. Cum sociis natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus. Donec quam felis, ultricies nec, pellentesque eu, pretium quis, sem. Nulla consequat massa quis enim.",
        },
        {
          img: eyeliner,
          title: "Light Eyeliner",
          description:
            "Lorem ipsum dolor sit amet, consectetuer adipiscing elit. Aenean commodo ligula eget dolor. Aenean massa. Cum sociis natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus. Donec quam felis, ultricies nec, pellentesque eu, pretium quis, sem. Nulla consequat massa quis enim.",
        },
        {
          img: eyeliner2,
          title: "Heavy Eyeliner",
          description:
            "Lorem ipsum dolor sit amet, consectetuer adipiscing elit. Aenean commodo ligula eget dolor. Aenean massa. Cum sociis natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus. Donec quam felis, ultricies nec, pellentesque eu, pretium quis, sem. Nulla consequat massa quis enim.",
        },
        {
          img: eyeshadow,
          title: "EyeShadow",
          description:
            "Lorem ipsum dolor sit amet, consectetuer adipiscing elit. Aenean commodo ligula eget dolor. Aenean massa. Cum sociis natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus. Donec quam felis, ultricies nec, pellentesque eu, pretium quis, sem. Nulla consequat massa quis enim.",
        },
        {
          img: mascara,
          title: "Mascara",
          description:
            "Lorem ipsum dolor sit amet, consectetuer adipiscing elit. Aenean commodo ligula eget dolor. Aenean massa. Cum sociis natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus. Donec quam felis, ultricies nec, pellentesque eu, pretium quis, sem. Nulla consequat massa quis enim.",
        },
        {
          img: rouge,
          title: "Rouge",
          description:
            "Lorem ipsum dolor sit amet, consectetuer adipiscing elit. Aenean commodo ligula eget dolor. Aenean massa. Cum sociis natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus. Donec quam felis, ultricies nec, pellentesque eu, pretium quis, sem. Nulla consequat massa quis enim.",
        },
      ],
    };
  },
  mounted() {
  },
};
</script>
<style>
#makeup-section {
}
article.card {
  width: 320px;
  margin: 0 auto;
}
img.card-img-top {
  width: 320px;
  height: 250px;
}
.section-title {
  font-size: 40px;
  font-weight: 900;
  margin: 20px 0;
}
.slick-dots li.slick-active button:before {
  color: pink;
}
h4.card-title {
  font-size: 25px;
  font-weight: 700;
}
p.card-text {
  font-size: 18px;
}
.VueCarousel-wrapper{
  overflow: unset;
}
@media (max-width: 400px) {
  article.card {
    width: 250px !important;
  }
  img.card-img-top {
    width: 250px !important;
    height: 180px !important;
  }
}
</style>
