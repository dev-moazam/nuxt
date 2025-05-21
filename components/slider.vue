<template>
  <Swiper
    :modules="[Navigation, Pagination, Autoplay]"
    :spaceBetween="20"
    :slidesPerView="1"
    :loop="true"
    :autoplay="{ delay: 3000 }"
    navigation
    pagination
    class="mySwiper"
  >
    <SwiperSlide v-for="(img, index) in images" :key="index">
      <img :src="img" alt="Slide Image" class="w-full h-auto rounded-lg object-cover" />
    </SwiperSlide>
  </Swiper>
</template>

<script setup>
import { Swiper, SwiperSlide } from 'swiper/vue'
import { Navigation, Pagination, Autoplay } from 'swiper/modules'
import 'swiper/css'
import 'swiper/css/navigation'
import 'swiper/css/pagination'

// Array of image paths
const images = [
  '/images/banner-image..webp',
  '/images/slide2.jpg',
  '/images/slide3.jpg',
  '/images/slide4.jpg',
  '/images/slide5.jpg',
]
</script>

<style scoped>
.mySwiper {
  width: 100%;
  height:600px;
  margin-bottom:10px;
}
</style>
