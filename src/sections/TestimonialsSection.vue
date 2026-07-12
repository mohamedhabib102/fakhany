<template>
  <section class="bg-[#faf9f6] py-16 px-6 relative overflow-hidden">
    <div class="max-w-[1400px] mx-auto relative z-10">
      
      <AnimatedElement direction="down" :delay="100">
        <SectionTitle theme="dark" align="center">
          آراء العملاء
      </SectionTitle>
      </AnimatedElement>

      <div class="grid grid-cols-1 md:grid-cols-3 gap-8">
        <AnimatedElement 
          v-for="(review, index) in reviews" 
          :key="index" 
          direction="up" 
          :delay="200 + (index * 200)"
        >
          <div class="bg-white p-8 rounded-xl shadow-sm hover:shadow-md transition-shadow border border-gray-100 flex flex-col items-center text-center h-full">
            
            <!-- Avatar (First Letter) -->
            <div class="w-16 h-16 rounded-full bg-gradient-to-br from-[#c29a53] to-[#e0be77] text-[#1b223d] flex items-center justify-center text-2xl font-black mb-4 font-cairo shadow-inner">
              {{ review.name.charAt(0) }}
            </div>
            
            <!-- Name -->
            <h3 class="font-bold text-lg text-[#1b223d] mb-2 font-cairo">{{ review.name }}</h3>
            
            <!-- Stars -->
            <div class="flex gap-1 text-[#c29a53] mb-4">
              <StarIcon v-for="i in 5" :key="i" class="w-4 h-4 fill-current" />
            </div>
            
            <!-- Feedback -->
            <p class="text-gray-600 text-sm leading-relaxed italic">
              "{{ review.text }}"
            </p>
            
          </div>
        </AnimatedElement>
      </div>

    </div>
  </section>
</template>

<script setup>
import AnimatedElement from '../components/AnimatedElement.vue'
import { Star as StarIcon } from 'lucide-vue-next'
import SectionTitle from '../components/SectionTitle.vue'

const reviews = [
  { name: 'أحمد محمود', text: 'فواكه طازجة جداً وتوصيل سريع في نفس اليوم. التغليف كان ممتازاً ووصلتني الفواكه مبردة وبأفضل جودة.' },
  { name: 'سارة خالد', text: 'الجودة لا يعلى عليها، والأسعار مناسبة جداً مقارنة بالسوق. أفضل متجر للفواكه الموسمية بلا منازع.' },
  { name: 'محمد علي', text: 'خدمة العملاء ممتازة وراقية جداً. جربت المانجو الإسماعيلاوي وكانت من أفضل ما تذوقت!' }
]
</script>
