<template>
  <swiper
    :pagination="pagination"
    :navigation="navigation"
    :modules="modules"
    class="mySwiper"
    :autoplay="{ delay: 5000 }"
  >
    <swiper-button-prev class="swiper-button-prev"></swiper-button-prev>
    <swiper-button-next class="swiper-button-next"></swiper-button-next>

    <swiper-slide v-for="(image, index) in images" :key="index">
      <div class="slide-content">
        <div class="text-container">
          <h6>{{ image.date }}</h6>
          <h2>{{ image.heading }}<span>&#8594;</span></h2>
          <p>{{ image.description }}</p>
        </div>
        <img :src="image.src" :alt="image.alt" />
      </div>
    </swiper-slide>
  </swiper>
</template>
<script>
import { Swiper, SwiperSlide } from "swiper/vue";
import "swiper/css";
import "swiper/css/pagination";
import "swiper/css/navigation"; // Add this line for navigation styles
import { Pagination, Navigation, Autoplay } from "swiper/modules";
import "./style.css";
export default {
  components: {
    Swiper,
    SwiperSlide,
  },
  setup() {
    const images = [
      {
        src: "Meet1.jpg",
        alt: "Slide 1",
        date: "14.02.2024 - Artigo",
        heading: "75 anos da Convencao Constitucional de Herrenchiemsee",
        description:
          "O Presidente da Alemanha. Frank-Walter Steinmeier.participant hoje(10/08)das comemoracoes dos 75 anos da Convencao Constitucional de Herrenchiemsee",
      },
      {
        src: "meet02.jpg",
        alt: "Slide 2",
        date: "14.02.2024 - Artigo",
        heading: "75 anos da Convencao Constitucional de Herrenchiemsee",
        description:
          "O Presidente da Alemanha. Frank-Walter Steinmeier.participant hoje(10/08)das comemoracoes dos 75 anos da Convencao Constitucional de Herrenchiemsee",
      },
      {
        src: "meet03.jpg",
        alt: "Slide 3",
        date: "14.02.2024 - Artigo",
        heading: "75 anos da Convencao Constitucional de Herrenchiemsee",
        description:
          "O Presidente da Alemanha. Frank-Walter Steinmeier.participant hoje(10/08)das comemoracoes dos 75 anos da Convencao Constitucional de Herrenchiemsee",
      },
    ];

    return {
      pagination: {
        clickable: true,
        renderBullet: function (index, className) {
          return '<span class="' + className + '">' + (index + 1) + "</span>";
        },
      },
      navigation: {
        nextEl: ".swiper-button-next",
        prevEl: ".swiper-button-prev",
      },
      modules: [Pagination, Navigation, Autoplay],
      images,
    };
  },
};
</script>

<style scoped>
.swiper-button-prev::after {
  content: "\2039"; /* Unicode character for left arrow */
}

.swiper-button-next::after {
  content: "\203A"; /* Unicode character for right arrow */
}

.swiper-pagination.swiper-pagination-clickable.swiper-pagination-bullets.swiper-pagination-horizontal {
  margin-left: 60px !important;
}
.slide-content {
  display: flex;
  align-items: center;
  justify-content: space-between;
  background-color: mintcream;
}

.text-container {
  margin-left: 20px;
  margin-bottom: 475px;
}
img {
  height: 600px;
}

h2[data-v-dac87bc3] {
  font-size: 25px;
  color: black;
  font-weight: bold;
  font-style: normal !important;
  margin-top: 10px;
}

span.swiper-pagination-bullet {
  font-size: 45px !important;
  font-weight: bold;
}
h2 {
  font-size: 35px;
  color: maroon;
  font-weight: bold;

  margin-top: 10px;
}

p {
  color: grey;
}
.swiper-pagination-bullet-active {
  color: #fff;
  background: white !important;
  -webkit-box-shadow: 10px 10px 5px 0px rgba(0, 0, 0, 0.11);
  -moz-box-shadow: 10px 10px 5px 0px rgba(0, 0, 0, 0.11);
  box-shadow: 10px 10px 5px 0px rgba(0, 0, 0, 0.11);
}
img[data-v-dac87bc3] {
  height: 600px;
  margin-bottom: 45px !important;
}

h6[data-v-dac87bc3] {
  font-size: 15px;
  color: gray;
  margin-left: 35px;
  background-color: #d3d3d3;
  line-height: 30px;
}

.swiper-button-prev {
  color: white;
  background: rgba(0, 0, 0, 0.3);
  cursor: pointer;
  margin-top: 307px !important;
  margin-left: 918px !important;
  height: 39px;
  width: 40px;
  border-radius: 5px;
  -webkit-box-shadow: 10px 10px 5px 0px rgba(0, 0, 0, 0.11);
  -moz-box-shadow: 10px 10px 5px 0px rgba(0, 0, 0, 0.11);
  box-shadow: 10px 10px 5px 0px rgba(0, 0, 0, 0.11);
  margin-bottom: 10px !important;
}
.swiper-button-next {
  color: white;
  font-size: 18px;
  background: rgba(0, 0, 0, 0.3);
  margin: 0 10px;
  margin-top: 307px;
  margin-right: 915px;
  height: 40px;
  width: 40px;
  border-radius: 5px;
  -webkit-box-shadow: 10px 10px 5px 0px rgba(0, 0, 0, 0.11);
  -moz-box-shadow: 10px 10px 5px 0px rgba(0, 0, 0, 0.11);
  box-shadow: 10px 10px 5px 0px rgba(0, 0, 0, 0.11);
  margin-bottom: 10px !important;
}
::after {
  margin-bottom: 10px !important;
}
</style>
