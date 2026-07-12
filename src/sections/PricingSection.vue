<template>
  <section id="pricing" class="bg-[#faf9f6] text-[#0a1428] py-16 px-6 md:px-12 select-none">
    <div class="max-w-7xl mx-auto w-full">
      <!-- Section Title -->
      <AnimatedElement direction="up" :delay="100">
        <SectionTitle theme="dark" align="center">
          باقات فواكه فاخرة
        </SectionTitle>
      </AnimatedElement>

      <!-- Pricing Cards Grid -->
      <div class="grid grid-cols-1 md:grid-cols-3 gap-8 mt-12 max-w-5xl mx-auto">
        <AnimatedElement 
          v-for="(plan, index) in plans" 
          :key="index"
          direction="up"
          :delay="200 + (index * 200)"
          class="h-full"
        >
          <div 
            class="flex flex-col h-full bg-white rounded-2xl border border-gray-200 p-6 md:p-8 shadow-md hover:shadow-xl hover:-translate-y-2 transition-all duration-300 relative group"
            :class="{ 'border-fakhany-gold ring-2 ring-fakhany-gold': plan.featured }"
          >
            <!-- Popular Ribbon -->
            <div 
            v-if="plan.featured" 
            class="absolute -top-3.5 left-4 bg-fakhany-gold text-fakhany-dark text-xs font-black px-3 py-1 rounded-full uppercase tracking-wider"
          >
            الأكثر طلباً
          </div>

          <!-- Plan Header -->
          <div class="mb-6">
            <h3 class="text-xl font-bold text-[#5a4835] group-hover:text-fakhany-gold transition-colors mb-2">
              {{ plan.name }}
            </h3>
            <div class="flex items-baseline gap-1 mt-3">
              <span class="text-4xl font-extrabold text-[#0a1428]">
                {{ plan.price }}
              </span>
              <span class="text-sm text-gray-500">/ صندوق</span>
            </div>
            <p class="text-sm text-gray-500 mt-2">
              {{ plan.description }}
            </p>
          </div>

          <!-- Plan Features -->
          <ul class="flex-grow flex flex-col gap-3 text-sm text-gray-600 mb-8 mt-2">
            <li v-for="(feature, fIdx) in plan.features" :key="fIdx" class="flex items-center gap-2">
              <CheckIcon class="w-4 h-4 text-fakhany-green stroke-[3] shrink-0" />
              <span>{{ feature }}</span>
            </li>
          </ul>

          <!-- Action Button -->
          <a href="https://wa.me/201027227796" target="_blank" class="block w-full mt-auto">
            <Button 
              :variant="plan.featured ? 'primary' : 'outline'" 
              class="w-full py-2.5 font-bold"
              :class="{'bg-fakhany-gold!': plan.featured}"
            >
              اطلب الآن
            </Button>
          </a>
          </div>
        </AnimatedElement>
      </div>
    </div>
  </section>
</template>

<script setup>
import AnimatedElement from '../components/AnimatedElement.vue'
import { Check as CheckIcon } from 'lucide-vue-next'
import SectionTitle from '../components/SectionTitle.vue'
import Button from '../components/Button.vue'

const plans = [
  {
    name: 'سلة التوفير العائلية',
    price: '$15',
    description: 'صندوق غني بالفواكه الأساسية الطازجة التي تناسب الاستهلاك العائلي اليومي.',
    features: [
      'موز بلدي وتفاح كلاسيك',
      'برتقال موسمي وعنب أحمر',
      'تغليف كرتوني صديق للبيئة',
      'توصيل مبرد قياسي خلال ٢٤ ساعة'
    ],
    featured: false
  },
  {
    name: 'السلة الموسمية الفاخرة',
    price: '$25',
    description: 'تشكيلة مختارة من أرقى وأندر فواكه الموسم الطازجة بجودة تصديرية.',
    features: [
      'مانجو إسمعيلي وبطيخ مرمل',
      'فراولة فاخرة وعنب وتين موسمي',
      'صندوق خشبي أنيق للتقديم',
      'شحن مبرد مجاني وفوري',
      'بطاقة هدايا مخصصة مجانية'
    ],
    featured: true
  },
  {
    name: 'سلة المناسبات والضيافة',
    price: '$45',
    description: 'سلة فاخرة جداً مصممة خصيصاً للمناسبات والضيافة الراقية مع فواكه نادرة.',
    features: [
      'جميع فواكه السلة الفاخرة',
      'إضافات استوائية (أناناس، باشن فروت)',
      'سلة خوص تقليدية فاخرة منسوجة يدوياً',
      'توصيل مبرد VIP بموعد محدد',
      'خدمة تنسيق وتقطيع مجانية متوفرة'
    ],
    featured: false
  }
]
</script>
