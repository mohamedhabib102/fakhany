<template>
  <section id="offers" class="relative w-full h-[120px] sm:h-[180px] md:h-[220px] overflow-hidden select-none my-4">
    <AnimatedElement direction="up" :delay="100" class="w-full h-full">
      <!-- Background Image -->
      <div 
        class="absolute inset-0 bg-cover bg-center transition-transform duration-[10000ms] hover:scale-105"
        :style="{ backgroundImage: `url(${offersBg})` }"
      ></div>

      <!-- Semi-transparent overlay to match colors -->
      <div class="absolute inset-0 bg-black/40 z-0"></div>

      <!-- Center Content -->
      <div class="relative z-10 w-full h-full flex items-center justify-center">
        <h2 
          class="text-3xl sm:text-5xl md:text-6xl font-black text-white drop-shadow-[0_5px_15px_rgba(0,0,0,0.8)] font-cairo text-center select-none tracking-wide"
        >
          عروض خاصة
        </h2>
      </div>
    </AnimatedElement>
  </section>
</template>

<script setup>
import offersBg from '../assets/images/offers_bg_1783855621613.png'
import AnimatedElement from '../components/AnimatedElement.vue'
</script>
