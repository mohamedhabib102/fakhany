<template>
  <footer class="bg-[#12182b] text-white py-12 px-6 md:px-12 border-t border-gray-800 select-none">
    <div class="max-w-[1400px] mx-auto flex flex-col md:flex-row justify-between items-start md:items-center gap-10">
      
      <!-- Right (RTL Left): Newsletter -->
      <div class="flex flex-col gap-3 w-full md:w-auto">
        <h4 class="text-[#c29a53] font-bold text-lg mb-1 font-cairo">القائمة البريدية</h4>
        <div class="flex items-center w-full max-w-sm rounded-md overflow-hidden border border-gray-600 focus-within:border-[#c29a53] transition-colors">
          <input 
            type="email" 
            placeholder="البريد الإلكتروني" 
            class="bg-transparent px-4 py-2 text-sm outline-none text-white w-full flex-grow placeholder-gray-400"
          />
          <button class="bg-[#c29a53] text-[#12182b] font-bold px-6 py-2 text-sm hover:bg-[#dfc28d] transition-colors h-full">
            اشتراك
          </button>
        </div>
      </div>

      <!-- Middle: Payment -->
      <div class="flex flex-col gap-3 items-start md:items-center w-full md:w-auto">
        <h4 class="text-[#c29a53] font-bold text-lg mb-1 font-cairo">طرق الدفع</h4>
        <div class="flex items-center gap-3">
          <!-- Visa-like -->
          <div class="bg-white px-3 py-1.5 rounded text-[#1a1f71] font-black italic text-sm shadow-sm w-12 h-8 flex items-center justify-center">VISA</div>
          <!-- Mastercard-like -->
          <div class="bg-white px-2 py-1.5 rounded flex items-center justify-center shadow-sm w-12 h-8">
            <div class="w-4 h-4 rounded-full bg-[#eb001b] opacity-90 relative z-10"></div>
            <div class="w-4 h-4 rounded-full bg-[#f79e1b] opacity-90 -mr-2 relative z-0"></div>
          </div>
          <!-- Amex-like -->
          <div class="bg-white px-1 py-1.5 rounded text-[#002663] font-bold text-[8px] text-center leading-none shadow-sm w-12 h-8 flex items-center justify-center">AMEX</div>
          <!-- Discover-like -->
          <div class="bg-white px-1 py-1.5 rounded text-[#f68121] font-bold italic text-[9px] shadow-sm w-12 h-8 flex items-center justify-center">Discover</div>
        </div>
      </div>

      <!-- Left (RTL Right): Contact (Social & Info) -->
      <div class="flex flex-col md:flex-row gap-10 md:gap-16 w-full md:w-auto">
        <div class="flex flex-col gap-3 items-start">
          <h4 class="text-[#c29a53] font-bold text-lg mb-1 font-cairo">تواصل معنا</h4>
          <div class="flex items-center gap-4 text-[#c29a53]">
            <a href="https://facebook.com" target="_blank" rel="noopener noreferrer" class="hover:text-white transition-colors">
              <svg class="w-5 h-5 fill-current" viewBox="0 0 24 24"><path d="M22 12c0-5.52-4.48-10-10-10S2 6.48 2 12c0 4.84 3.44 8.87 8 9.8V15H8v-3h2V9.5C10 7.57 11.57 6 13.5 6H16v3h-2c-.55 0-1 .45-1 1v2h3v3h-3v6.95c4.56-.93 8-4.96 8-9.75z"/></svg>
            </a>
            <a href="https://instagram.com" target="_blank" rel="noopener noreferrer" class="hover:text-white transition-colors">
              <svg class="w-5 h-5" fill="none" stroke="currentColor" stroke-width="2"><rect x="2" y="2" width="20" height="20" rx="5" ry="5"></rect><path d="M16 11.37A4 4 0 1 1 12.63 8 4 4 0 0 1 16 11.37z"></path><line x1="17.5" y1="6.5" x2="17.51" y2="6.5"></line></svg>
            </a>
            <a href="https://linkedin.com" target="_blank" rel="noopener noreferrer" class="hover:text-white transition-colors">
              <svg class="w-5 h-5 fill-current" viewBox="0 0 24 24"><path d="M19 0h-14c-2.761 0-5 2.239-5 5v14c0 2.761 2.239 5 5 5h14c2.762 0 5-2.239 5-5v-14c0-2.761-2.238-5-5-5zm-11 19h-3v-11h3v11zm-1.5-12.268c-.966 0-1.75-.779-1.75-1.75s.784-1.75 1.75-1.75 1.75.779 1.75 1.75-.784 1.75-1.75 1.75zm13.5 12.268h-3v-5.604c0-3.368-4-3.113-4 0v5.604h-3v-11h3v1.765c1.396-2.586 7-2.777 7 2.476v6.759z"/></svg>
            </a>
          </div>
        </div>

        <div class="flex flex-col gap-3 items-start text-sm text-gray-300">
          <h4 class="text-[#c29a53] font-bold text-lg mb-1 font-cairo">اتصل بنا</h4>
          <div class="flex items-center gap-3">
            <PhoneIcon class="w-4 h-4 text-[#c29a53]" />
            <span dir="ltr">+91 2238399</span>
          </div>
          <div class="flex items-center gap-3">
            <MailIcon class="w-4 h-4 text-[#c29a53]" />
            <span>info@fakhany.com</span>
          </div>
          <div class="flex items-center gap-3">
            <GlobeIcon class="w-4 h-4 text-[#c29a53]" />
            <span>www.fakhany.com</span>
          </div>
        </div>
      </div>

    </div>
  </footer>
</template>

<script setup>
import { 
  Phone as PhoneIcon, 
  Mail as MailIcon, 
  Globe as GlobeIcon 
} from 'lucide-vue-next'
</script>
