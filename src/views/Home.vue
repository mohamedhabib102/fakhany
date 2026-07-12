<template>
  <div class="flex flex-col min-h-screen">
    <!-- Header / Navbar -->
    <Navbar />

    <!-- Main Content Area -->
    <main class="grow flex flex-col items-center w-full">
      <!-- 1. Hero Slider Section (Keep as is) -->
      <HeroSection />

      <!-- 2. Mid Grid Section (Best Sellers on Right, Why Choose Us on Left) -->
      <div class="max-w-350 w-full grid grid-cols-1 lg:grid-cols-2">
        <AboutSection />
        <ServicesSection />
      </div>

      <!-- 3. Special Offers Banner -->
      <FeaturesSection />


      
      <!-- 4. Testimonials -->
      <TestimonialsSection />
      
    </main>
    <PricingSection/>

    <!-- Footer Area -->
    <Footer />
  </div>
</template>

<script setup>
// Import layout components
import Navbar from '../components/Navbar.vue'
import Footer from '../components/Footer.vue'

// Import sections
import HeroSection from '../sections/HeroSection.vue'
import ServicesSection from '../sections/ServicesSection.vue' // Sells / Best Sellers
import AboutSection from '../sections/AboutSection.vue'       // Features / لماذا نتميز
import FeaturesSection from '../sections/FeaturesSection.vue'   // Offers / عروض خاصة banner
import TestimonialsSection from '../sections/TestimonialsSection.vue'
import PricingSection from '../sections/PricingSection.vue'
</script>
