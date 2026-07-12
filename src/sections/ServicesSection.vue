<template>
  <section class="bg-[#1b223d] text-white py-12 px-6 flex flex-col items-center h-full w-full overflow-hidden">
    <div class="w-full text-center max-w-350">
      <AnimatedElement direction="up" :delay="100" trigger="mount">
        <h2 class="text-2xl md:text-3xl font-bold mb-10 tracking-wide font-cairo text-white">
          الأكثر مبيعاً
        </h2>
      </AnimatedElement>

      <!-- Products Slider (Multiple items) -->
      <div class="w-full mt-4">
        <AnimatedElement direction="up" :delay="300">
          <swiper
            :slides-per-view="2"
            :space-between="20"
            :breakpoints="{
              '640': { slidesPerView: 3, spaceBetween: 20 },
              '1024': { slidesPerView: 4, spacespaceBetween: 30 }
            }"
            :loop="true"
            :autoplay="{ delay: 3500, disableOnInteraction: false }"
            :modules="[Autoplay]"
            class="w-full py-4 cursor-grab active:cursor-grabbing"
          >
            <swiper-slide v-for="(product, index) in products" :key="index">
              <div class="flex flex-col items-center text-center group py-2">
                <!-- Product Image (Pedestal) -->
                <div class="w-28 sm:w-36 md:w-44 flex items-center justify-center relative mb-4">
                  <img 
                    :src="product.image" 
                    :alt="product.name" 
                    class="w-full h-auto object-contain transform group-hover:scale-105 transition-transform duration-300 drop-shadow-xl"
                  />
                </div>

                <!-- Product Info -->
                <h3 class="font-bold text-sm sm:text-base text-white mb-2 font-cairo">
                  {{ product.name }}
                </h3>

                <!-- Stars Rating -->
                <div class="flex items-center gap-[2px] mb-3">
                  <span v-for="star in 5" :key="star" class="text-xs">
                    <StarIcon class="w-3 h-3 text-fakhany-gold fill-fakhany-gold" />
                  </span>
                </div>

                <!-- Price Box -->
                <div class="border border-[#c29a53] px-4 py-1 text-xs md:text-sm font-bold text-[#c29a53] tracking-widest rounded-sm">
                  {{ product.price }}
                </div>
              </div>
            </swiper-slide>
          </swiper>
        </AnimatedElement>
      </div>
    </div>
  </section>
</template>

<script setup>
import AnimatedElement from '../components/AnimatedElement.vue'
import { Swiper, SwiperSlide } from 'swiper/vue'
import { Autoplay } from 'swiper/modules'
import 'swiper/css'

import { Star as StarIcon } from 'lucide-vue-next'

import mangoImg from '../assets/images/mango_pedestal_1783855603541.png'
import strawberryImg from '../assets/images/strawberry_pedestal_1783855573067.png'
import bananaImg from '../assets/images/banana.png'
import watermelonImg from '../assets/images/watermelon.png'
import grapesImg from '../assets/images/grapes.png'

const products = [
  {
    name: 'مانجو إسماعيلاوي',
    image: mangoImg,
    price: '$2.50'
  },
  {
    name: 'فراولة فاخرة',
    image: strawberryImg,
    price: '$5.50'
  },
  {
    name: 'موز بلدي',
    image: bananaImg,
    price: '$1.50'
  },
  {
    name: 'بطيخ مرمل',
    image: watermelonImg,
    price: '$3.00'
  },
  {
    name: 'عنب بناتي',
    image: grapesImg,
    price: '$4.00'
  },
  {
    name: 'مانجو عويس',
    image: mangoImg,
    price: '$3.50'
  },
  {
    name: 'فراولة بلدي',
    image: strawberryImg,
    price: '$4.00'
  }
]
</script>
