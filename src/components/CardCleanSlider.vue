<template>
  <div id="skincare-section">
    <div class="section-title">Skin care section</div>
    <Carousel
      ref="slider"
      :perPageCustom="[[900, 3], [700, 2] , [100, 1]]"
      :paginationEnabled="true"
      :paginationActiveColor="paginationColor"
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
import "vue-slick-carousel/dist/vue-slick-carousel.css";
import "vue-slick-carousel/dist/vue-slick-carousel-theme.css";
import bodyLotion from "../assets/skinCareSection/bodyLotion.jpg";
import cleanser from "../assets/skinCareSection/cleanser.jpg";
import guasha from "../assets/skinCareSection/guashaTool.jpg";
import moistriser from "../assets/skinCareSection/moistriser.jpg";
import serum from "../assets/skinCareSection/serum.jpg";
import sunCream from "../assets/skinCareSection/sunCream.jpg";
import toner from "../assets/skinCareSection/toner.jpg";
import { Carousel, Slide } from "vue-carousel";
export default {
  name: "MyComponent",
  components: { Carousel, Slide },
  data() {
    return {
      paginationColor: "pink",
      perPage: 3,
      data: [
        {
          img: bodyLotion,
          title: "Body Lotion",
          description:
            "Lorem ipsum dolor sit amet, consectetuer adipiscing elit. Aenean commodo ligula eget dolor. Aenean massa. Cum sociis natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus. Donec quam felis, ultricies nec, pellentesque eu, pretium quis, sem. Nulla consequat massa quis enim.",
        },
        {
          img: cleanser,
          title: "Cleanser",
          description:
            "Lorem ipsum dolor sit amet, consectetuer adipiscing elit. Aenean commodo ligula eget dolor. Aenean massa. Cum sociis natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus. Donec quam felis, ultricies nec, pellentesque eu, pretium quis, sem. Nulla consequat massa quis enim.",
        },
        {
          img: guasha,
          title: "Guasha Tools ",
          description:
            "Lorem ipsum dolor sit amet, consectetuer adipiscing elit. Aenean commodo ligula eget dolor. Aenean massa. Cum sociis natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus. Donec quam felis, ultricies nec, pellentesque eu, pretium quis, sem. Nulla consequat massa quis enim.",
        },
        {
          img: moistriser,
          title: "Moisturizer",
          description:
            "Lorem ipsum dolor sit amet, consectetuer adipiscing elit. Aenean commodo ligula eget dolor. Aenean massa. Cum sociis natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus. Donec quam felis, ultricies nec, pellentesque eu, pretium quis, sem. Nulla consequat massa quis enim.",
        },
        {
          img: serum,
          title: "Serum",
          description:
            "Lorem ipsum dolor sit amet, consectetuer adipiscing elit. Aenean commodo ligula eget dolor. Aenean massa. Cum sociis natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus. Donec quam felis, ultricies nec, pellentesque eu, pretium quis, sem. Nulla consequat massa quis enim.",
        },
        {
          img: sunCream,
          title: "Sun Cream",
          description:
            "Lorem ipsum dolor sit amet, consectetuer adipiscing elit. Aenean commodo ligula eget dolor. Aenean massa. Cum sociis natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus. Donec quam felis, ultricies nec, pellentesque eu, pretium quis, sem. Nulla consequat massa quis enim.",
        },
        {
          img: toner,
          title: "Toner",
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
#section-title {
}
article.card {
  width: 320px;
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
</style>
