<template>
  <section id="contact" class="bg-[#faf9f6] text-[#0a1428] py-16 px-6 md:px-12 select-none border-t border-gray-200">
    <div 
      class="max-w-6xl mx-auto w-full"
    >
      <SectionTitle theme="dark" align="center">
        تواصل معنا
      </SectionTitle>

      <div class="mt-12 grid grid-cols-1 md:grid-cols-2 gap-12 bg-white rounded-2xl shadow-lg border border-gray-100 overflow-hidden">
        
        <!-- Contact Form -->
        <div class="p-8 md:p-12">
          <h3 class="text-2xl font-bold text-fakhany-dark mb-6">يسعدنا تواصلكم!</h3>
          <form @submit.prevent class="flex flex-col gap-5">
            <div class="flex flex-col gap-2">
              <label class="text-sm font-semibold text-gray-700">الاسم الكريم</label>
              <input type="text" placeholder="اكتب اسمك هنا" class="border border-gray-300 px-4 py-3 rounded-lg focus:outline-none focus:ring-2 focus:ring-fakhany-gold transition-shadow" />
            </div>
            
            <div class="flex flex-col gap-2">
              <label class="text-sm font-semibold text-gray-700">رقم الهاتف</label>
              <input type="tel" placeholder="+20 123 456 7890" dir="ltr" class="border border-gray-300 px-4 py-3 rounded-lg focus:outline-none focus:ring-2 focus:ring-fakhany-gold transition-shadow text-right" />
            </div>

            <div class="flex flex-col gap-2">
              <label class="text-sm font-semibold text-gray-700">رسالتك</label>
              <textarea placeholder="كيف يمكننا مساعدتك؟" rows="4" class="border border-gray-300 px-4 py-3 rounded-lg focus:outline-none focus:ring-2 focus:ring-fakhany-gold transition-shadow resize-none"></textarea>
            </div>

            <Button variant="primary" class="mt-2 py-3 font-bold shadow-md hover:shadow-lg">
              إرسال الرسالة
            </Button>
          </form>
        </div>

        <!-- Contact Info & Map Mock -->
        <div class="bg-fakhany-dark text-white p-8 md:p-12 flex flex-col justify-between relative overflow-hidden">
          <div class="absolute inset-0 opacity-10 bg-[url('https://www.transparenttextures.com/patterns/cubes.png')] pointer-events-none"></div>
          
          <div class="relative z-10">
            <h3 class="text-2xl font-bold text-fakhany-gold mb-8">معلومات التواصل</h3>
            
            <div class="flex flex-col gap-6">
              <div class="flex items-start gap-4">
                <div class="w-10 h-10 rounded-full bg-fakhany-gold/20 flex items-center justify-center text-fakhany-gold shrink-0">
                  <MapPinIcon class="w-5 h-5" />
                </div>
                <div>
                  <h4 class="font-bold text-lg mb-1">الفرع الرئيسي</h4>
                  <p class="text-gray-300 text-sm">شطر الحي الثامن، مدينة نصر<br />القاهرة، مصر</p>
                </div>
              </div>

              <div class="flex items-start gap-4">
                <div class="w-10 h-10 rounded-full bg-fakhany-gold/20 flex items-center justify-center text-fakhany-gold shrink-0">
                  <PhoneIcon class="w-5 h-5" />
                </div>
                <div>
                  <h4 class="font-bold text-lg mb-1">الخط الساخن</h4>
                  <p class="text-gray-300 text-sm" dir="ltr">+20 100 123 4567</p>
                </div>
              </div>

              <div class="flex items-start gap-4">
                <div class="w-10 h-10 rounded-full bg-fakhany-gold/20 flex items-center justify-center text-fakhany-gold shrink-0">
                  <ClockIcon class="w-5 h-5" />
                </div>
                <div>
                  <h4 class="font-bold text-lg mb-1">ساعات العمل</h4>
                  <p class="text-gray-300 text-sm">يومياً من ٩ صباحاً حتى ١١ مساءً</p>
                </div>
              </div>
            </div>
          </div>
          
          <div class="relative z-10 mt-12 pt-8 border-t border-white/10">
            <p class="text-sm text-gray-400">
              تابعنا على منصات التواصل الاجتماعي للحصول على أحدث العروض والمنتجات.
            </p>
          </div>
        </div>

      </div>
    </div>
  </section>
</template>

<script setup>
import { MapPin as MapPinIcon, Phone as PhoneIcon, Clock as ClockIcon } from 'lucide-vue-next'
import SectionTitle from '../components/SectionTitle.vue'
import Button from '../components/Button.vue'
</script>
