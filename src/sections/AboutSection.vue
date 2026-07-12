<template>
  <section class="bg-[#faf9f6] py-12 md:py-16 px-6">
    <div class="max-w-5xl mx-auto flex flex-col items-center text-center">
      
      <AnimatedElement direction="up" :delay="100" trigger="mount">
        <h2 class="text-2xl md:text-4xl font-bold text-fakhany-dark mb-10 font-cairo">
          لماذا نتميز؟
        </h2>
      </AnimatedElement>

      <!-- Features Grid (1 Row) -->
      <div class="flex flex-row justify-center items-center gap-4 sm:gap-8 md:gap-12">
        
        <!-- Feature 4: Customer Service (First on Right) -->
        <AnimatedElement direction="up" :delay="200">
          <div class="flex flex-col items-center gap-3">
            <div class="w-16 h-16 sm:w-20 sm:h-20 rounded-full border-[3px] border-[#c29a53] bg-[#1b223d] flex items-center justify-center text-[#c29a53] shadow-md">
              <HeadsetIcon class="w-8 h-8 sm:w-10 sm:h-10" />
            </div>
            <span class="font-bold text-sm sm:text-base text-[#1b223d]">
              خدمة عملاء
            </span>
          </div>
        </AnimatedElement>

        <!-- Feature 3: Refrigerated Delivery -->
        <AnimatedElement direction="up" :delay="350">
          <div class="flex flex-col items-center gap-3">
            <div class="w-16 h-16 sm:w-20 sm:h-20 rounded-full border-[3px] border-[#c29a53] bg-[#1b223d] flex items-center justify-center text-[#c29a53] shadow-md">
              <TruckIcon class="w-8 h-8 sm:w-10 sm:h-10" />
            </div>
            <span class="font-bold text-sm sm:text-base text-[#1b223d]">
              توصيل مبرد
            </span>
          </div>
        </AnimatedElement>

        <!-- Feature 2: High Quality -->
        <AnimatedElement direction="up" :delay="500">
          <div class="flex flex-col items-center gap-3">
            <div class="w-16 h-16 sm:w-20 sm:h-20 rounded-full border-[3px] border-[#c29a53] bg-[#1b223d] flex items-center justify-center text-[#c29a53] shadow-md">
              <AwardIcon class="w-8 h-8 sm:w-10 sm:h-10" />
            </div>
            <span class="font-bold text-sm sm:text-base text-[#1b223d]">
              جودة عالية
            </span>
          </div>
        </AnimatedElement>

        <!-- Feature 1: Fresh Daily (Last on Left) -->
        <AnimatedElement direction="up" :delay="650">
          <div class="flex flex-col items-center gap-3">
            <div class="w-16 h-16 sm:w-20 sm:h-20 rounded-full border-[3px] border-[#c29a53] bg-[#1b223d] flex items-center justify-center text-[#c29a53] shadow-md">
              <LeafIcon class="w-8 h-8 sm:w-10 sm:h-10" />
            </div>
            <span class="font-bold text-sm sm:text-base text-[#1b223d]">
              طازجة يومياً
            </span>
          </div>
        </AnimatedElement>

      </div>
    </div>
  </section>
</template>

<script setup>
import AnimatedElement from '../components/AnimatedElement.vue'
import { 
  Headset as HeadsetIcon, 
  Truck as TruckIcon, 
  BadgeCheck as AwardIcon, 
  Leaf as LeafIcon 
} from 'lucide-vue-next'
</script>
