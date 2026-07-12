<template>
  <section class="bg-white py-12 md:py-16 px-6">
    <div class="max-w-5xl mx-auto flex flex-col items-center text-center">
      
      <AnimatedElement direction="up" :delay="100" trigger="mount">
        <h2 class="text-2xl md:text-4xl font-bold text-fakhany-dark mb-10 font-cairo">
          لماذا نتميز؟
        </h2>
      </AnimatedElement>

      <!-- Features Grid (1 Row) -->
      <div class="flex flex-row justify-center items-center gap-6 sm:gap-10">
        
        <!-- Feature 4: Customer Service (First on Right) -->
        <AnimatedElement direction="up" :delay="200">
          <div class="flex flex-col items-center gap-3">
            <div class="w-16 h-16 rounded-full border-2 border-fakhany-gold bg-[#1b223d] flex items-center justify-center text-fakhany-gold shadow-md">
              <HeadsetIcon class="w-8 h-8 stroke-[1.5]" />
            </div>
            <span class="font-bold text-sm text-[#1b223d]">
              خدمة عملاء
            </span>
          </div>
        </AnimatedElement>

        <!-- Feature 3: Refrigerated Delivery -->
        <AnimatedElement direction="up" :delay="350">
          <div class="flex flex-col items-center gap-3">
            <div class="w-16 h-16 rounded-full border-2 border-fakhany-gold bg-[#1b223d] flex items-center justify-center text-fakhany-gold shadow-md">
              <TruckIcon class="w-8 h-8 stroke-[1.5]" />
            </div>
            <span class="font-bold text-sm text-[#1b223d]">
              توصيل مبرد
            </span>
          </div>
        </AnimatedElement>

        <!-- Feature 2: High Quality -->
        <AnimatedElement direction="up" :delay="500">
          <div class="flex flex-col items-center gap-3">
            <div class="w-16 h-16 rounded-full border-2 border-fakhany-gold bg-[#1b223d] flex items-center justify-center text-fakhany-gold shadow-md">
              <AwardIcon class="w-8 h-8 stroke-[1.5] fill-fakhany-gold/20" />
            </div>
            <span class="font-bold text-sm text-[#1b223d]">
              جودة عالية
            </span>
          </div>
        </AnimatedElement>

        <!-- Feature 1: Fresh Daily (Last on Left) -->
        <AnimatedElement direction="up" :delay="650">
          <div class="flex flex-col items-center gap-3">
            <div class="w-16 h-16 rounded-full border-2 border-fakhany-gold bg-[#1b223d] flex items-center justify-center text-fakhany-gold shadow-md">
              <LeafIcon class="w-8 h-8 stroke-[1.5] fill-fakhany-gold/20" />
            </div>
            <span class="font-bold text-sm text-[#1b223d]">
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
  Headphones as HeadsetIcon, 
  Truck as TruckIcon, 
  Award as AwardIcon, 
  Leaf as LeafIcon 
} from 'lucide-vue-next'
</script>
