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
        heading: "Nota de imprensa- Dia de Africa",
        description: "Nota de imprensa- Dia de Africa 14.02.2024",
      },
      {
        src: "meet02.jpg",
        alt: "Slide 2",
        heading: "Nota de imprensa- Dia de Africa",
        description: "Nota de imprensa- Dia de Africa 14.02.2024",
      },
      {
        src: "meet03.jpg",
        alt: "Slide 3",
        heading: "Nota de imprensa- Dia de Africa",
        description: "Nota de imprensa- Dia de Africa 14.02.2024",
      },
    ];

    return {
      pagination: {
        clickable: true,
        renderBullet: function (index, className) {
          return '<span class="' + className + '">' + (index + 1) + "</span>";
        },
      },
      modules: [Pagination, Navigation, Autoplay],
      images,
    };
  },
};
</script>
<style>
.mySwiper {
  background-image: url("water.jpg");
  background-size: cover;
  background-position: center;
}

.swiper-pagination-bullet {
  opacity: 0.7;
}
.swiper-pagination.swiper-pagination-clickable.swiper-pagination-bullets.swiper-pagination-horizontal {
  margin-left: 50px;
}
</style>
