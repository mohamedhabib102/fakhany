<template>
  <nav class="bg-[#faf9f6] border-b border-gray-200 py-3 px-6 md:px-12 flex flex-row items-center justify-between shadow-sm sticky top-0 z-50">
    <!-- Right Side in RTL (First in HTML): Branches Link and Delivery Button -->
    <div class="flex-1 flex items-center justify-start gap-4 md:gap-6">
      <a href="https://wa.me/201027227796" target="_blank" class="block">
        <Button variant="primary" class="text-sm md:text-base px-4 md:px-6 py-1.5 md:py-2 font-bold flex items-center gap-2">
          <TruckIcon class="w-4 h-4" />
          توصيل
        </Button>
      </a>
      <a href="https://wa.me/201027227796" target="_blank" class="text-fakhany-dark hover:text-fakhany-gold transition-colors font-semibold text-sm md:text-base hidden sm:inline-block">
        خدمة الفروع
      </a>
    </div>

    <!-- Center: Brand Logo with Gold Monogram F -->
    <div class="flex-shrink-0 flex flex-col items-center">
      <a href="#" class="flex flex-col items-center group">
        <!-- Logo Icon - A clean, stylized golden F logo -->
        <div class="flex items-center justify-center border-2 border-fakhany-gold rounded-md w-8 h-8 md:w-9 md:h-9 rotate-45 transition-transform duration-300 group-hover:rotate-90">
          <span class="-rotate-45 text-lg md:text-xl font-extrabold text-fakhany-gold leading-none font-serif">F</span>
        </div>
        <span class="text-sm md:text-base font-black tracking-widest text-[#5a4835] uppercase mt-1">FAKHANY</span>
      </a>
    </div>

    <!-- Left Side in RTL (Last in HTML): Links and Shopping Cart Icon -->
    <div class="flex-1 flex items-center justify-end gap-4 md:gap-6">
      <div class="hidden md:flex items-center gap-6 text-[#5a4835] font-semibold text-sm md:text-base">
        <a href="#pricing" class="hover:text-fakhany-gold transition-colors duration-200">الفواكه الموسمية</a>
        <a href="#best-sellers" class="hover:text-fakhany-gold transition-colors duration-200">الأكثر مبيعاً</a>
      </div>
      <button class="text-fakhany-gold hover:text-fakhany-goldLight transition-colors relative cursor-pointer focus:outline-none">
        <ShoppingBagIcon class="w-6 h-6 stroke-[2]" />
        <span class="absolute -top-1.5 -right-1.5 bg-fakhany-green text-white text-[10px] w-4 h-4 rounded-full flex items-center justify-center font-bold">0</span>
      </button>
    </div>
  </nav>
</template>

<script setup>
import { ShoppingBag as ShoppingBagIcon, Truck as TruckIcon } from 'lucide-vue-next'
import Button from './Button.vue'
</script>
