<template>
  <section class="relative w-full h-[500px] md:h-[700px] overflow-idden select-none bg-cover bg-center" :style="{ backgroundImage: `url(${heroBg})` }">
    <!-- Subtle light overlay to ensure text readability without darkening the whole image -->
    <div class="absolute inset-0 bg-white/10 z-0"></div>

    <swiper
      :slides-per-view="1"
      :space-between="0"
      :loop="true"
      :autoplay="{ delay: 4000, disableOnInteraction: false }"
      :modules="[Autoplay]"
      class="w-full h-full cursor-grab active:cursor-grabbing relative z-10"
    >
      <swiper-slide v-for="(slide, index) in slides" :key="index">
        <div class="w-full h-full flex flex-col justify-start items-center pt-12 md:pt-20 px-6 relative">
          
          <!-- Top Title -->
          <div class="w-full text-center z-20 mb-8 md:mb-12">
            <AnimatedElement direction="down" trigger="mount" :delay="300">
              <h1 class="text-4xl sm:text-5xl md:text-6xl lg:text-7xl font-black text-[#1b223d] leading-tight font-cairo drop-shadow-sm">
                {{ slide.title }}
              </h1>
            </AnimatedElement>
          </div>

          <!-- Center Image & Bottom Button (Flexbox without absolute) -->
          <div class="grow flex flex-col md:flex-row w-full pb-6 md:pb-10 items-center md:items-end justify-end">
            
            <!-- Desktop Left Spacer (RTL Right side) to keep image centered -->
            <div class="hidden md:block md:flex-1"></div>

            <!-- Image Center -->
            <div class="w-full md:flex-[2] flex justify-center">
              <AnimatedElement direction="up" trigger="mount" :delay="600">
                <img
                  :src="slide.image"
                  :alt="slide.title"
                  :class="['object-contain drop-shadow-[0_20px_30px_rgba(0,0,0,0.4)]', slide.imageClass]"
                />
              </AnimatedElement>
            </div>

            <!-- Button Container: Mobile (justify-start = RTL Right), Desktop (justify-end = RTL Left) -->
            <div class="w-full md:flex-1 flex justify-start md:justify-end mt-8 md:mt-0 px-2 md:px-0 z-20">
              <AnimatedElement direction="left" trigger="mount" :delay="900">
                <a href="https://wa.me/201027227796" target="_blank"  class="bg-[#3b6045] text-white block text-sm md:text-lg px-8 py-2.5 font-bold rounded-full border-2 border-[#c29a53] hover:bg-[#2c4a34] transition-colors shadow-lg">
                  تسوق الآن
                </a>
              </AnimatedElement>
            </div>

          </div>

        </div>
      </swiper-slide>
    </swiper>
  </section>
</template>

<script setup>
import AnimatedElement from '../components/AnimatedElement.vue'
import { Swiper, SwiperSlide } from 'swiper/vue'
import { Autoplay } from 'swiper/modules'
import 'swiper/css'

// Import assets
import heroBg from '../assets/images/hero.png'
import fruitBowl from '../assets/images/fruit_bowl_1783855563521.png'
import apple from '../assets/images/hero-one.png'
import watermelon from '../assets/images/hero-four.png'
import grapes from '../assets/images/hero-tow.png'
import banana from '../assets/images/hero-three.png'

const slides = [
  {
    title: 'طازجة من المزرعة لبيتك',
    image: fruitBowl,
    imageClass: 'w-[280px] sm:w-[350px] md:w-[450px] lg:w-[550px]'
  },
  {
    title: 'تفاح أحمر فاخر ولذيذ',
    image: apple,
    imageClass: 'w-[220px] sm:w-[280px] md:w-[350px] lg:w-[400px]'
  },
  {
    title: 'بطيخ مرمل منعش ومحلي',
    image: watermelon,
    imageClass: 'w-[220px] sm:w-[280px] md:w-[350px] lg:w-[400px]'
  },
  {
    title: 'عنب فاخر عالي الجودة',
    image: grapes,
    imageClass: 'w-[220px] sm:w-[280px] md:w-[350px] lg:w-[400px]'
  },
  {
    title: 'موز بلدي غني بالطاقة',
    image: banana,
    imageClass: 'w-[220px] sm:w-[280px] md:w-[350px] lg:w-[400px]'
  }
]
</script>

<style scoped>
/* Ensure smooth transitions inside Swiper slides */
.swiper-slide {
  backface-visibility: hidden;
}
</style>
