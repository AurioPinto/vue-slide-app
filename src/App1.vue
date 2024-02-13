<template>
  <swiper
    :pagination="pagination"
    :modules="modules"
    class="mySwiper"
    :autoplay="{ delay: 5000 }"
  >
    <swiper-slide v-for="(image, index) in images" :key="index">
      <div class="slide-content">
        <div class="text-container">
          <h2>{{ image.heading }}</h2>
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
import { Pagination, Autoplay } from "swiper/modules";
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
        heading: "75 anos da Convencao Constitucional de Herrenchiemsee",
        description:
          "O Presidente da Alemanha. Frank-Walter Steinmeier.participant hoje(10/08)das comemoracoes dos 75 anos da Convencao Constitucional de Herrenchiemsee",
      },
      {
        src: "meet02.jpg",
        alt: "Slide 2",
        heading: "Nota de imprensa- Dia de Africa",
        description: "Nota de imprensa- Dia de Africa",
      },
      {
        src: "meet03.jpg",
        alt: "Slide 3",
        heading: "Nota de imprensa- Dia de Africa",
        description: "Nota de imprensa- Dia de Africa",
      },
    ];

    return {
      pagination: {
        clickable: true,
        renderBullet: function (index, className) {
          return '<span class="' + className + '">' + (index + 1) + "</span>";
        },
      },
      modules: [Pagination, Autoplay],
      images,
    };
  },
};
</script>

<style scoped>
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
</style>
