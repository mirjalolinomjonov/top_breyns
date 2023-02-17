<template>
  <Carousel :items-to-show="2.5" :wrap-around="true">
    <Slide v-for="slide in 10" :key="slide">
      <div class="carousel__item">{{ slide }}</div>
      <!-- <teacher-info /> -->
    </Slide>

    <template #addons>
      <Navigation />
    </template>
  </Carousel>
</template>

<script>
import { defineComponent } from "vue";
import { Carousel, Navigation, Slide } from "vue3-carousel";
// import "vue3-carousel/carousel.css";

import TeacherInfo from "../TeacherInfo.vue";

export default defineComponent({
  name: "WrapAround",
  components: {
    Carousel,
    Slide,
    Navigation,
    TeacherInfo,
  },
});
</script>
