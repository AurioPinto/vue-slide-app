<template>
  <swiper
    :pagination="pagination"
    :modules="modules"
    class="mySwiper"
    :autoplay="{ delay: 5000 }"
  >
    <swiper-slide v-for="(image, index) in images" :key="index">
      <div class="slide-content">
        <img :src="image.src" :alt="image.alt" />
        <div class="text-container">
          <h2>{{ image.heading }}</h2>
          <p>{{ image.description }}</p>
        </div>
      </div>
    </swiper-slide>
  </swiper>
</template>

<script>
import { Swiper, SwiperSlide } from "swiper/vue";
import "swiper/css";
import "swiper/css/pagination";
import { Pagination } from "swiper/modules";
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
        heading: "Nota de imprensa- Dia de Africa",
        description: "Nota de imprensa- Dia de Africa",
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
      modules: [Pagination],
      images,
    };
  },
};
</script>
