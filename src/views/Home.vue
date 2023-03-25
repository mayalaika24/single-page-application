<template>
  <div class="home">
    <Nav />
    <HomeSlider />
    <CardSlider />
    <CardCleanSlider />
    <FeedBack />
    <Footer />
  </div>
</template>

<script>
import Nav from "../components/Nav";
import HomeSlider from "../components/HomeSlider";
import CardSlider from "../components/CardSlider";
import CardCleanSlider from "../components/CardCleanSlider";
import FeedBack from "../components/FeedBack";
import Footer from "../components/Footer";
export default {
  name: "Home",
  components: {
    Nav,
    HomeSlider,
    CardSlider,
    CardCleanSlider,
    FeedBack,
    Footer,
  },
};
</script>
<style>
@font-face {
  font-family: alex;
  src: url('../assets/font/Alex_Brush/AlexBrush-Regular.ttf');
}
.home{
  font-family: alex;
}
.section-title{
  text-align: center;
}
</style>
