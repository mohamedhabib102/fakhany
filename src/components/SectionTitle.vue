<template>
  <div :class="['flex flex-col mb-8', alignClass]">
    <h2 :class="['text-2xl md:text-3xl font-extrabold tracking-wide uppercase', colorClass]">
      <slot></slot>
    </h2>
    <div :class="['w-16 h-1 mt-2 rounded-full', lineClass]"></div>
  </div>
</template>

<script setup>
import { computed } from 'vue'

const props = defineProps({
  align: {
    type: String,
    default: 'center' // 'center' | 'right' | 'left'
  },
  theme: {
    type: String,
    default: 'light' // 'light' (for dark background) | 'dark' (for white background)
  }
})

const alignClass = computed(() => {
  if (props.align === 'right') return 'items-start text-right'
  if (props.align === 'left') return 'items-end text-left'
  return 'items-center text-center'
})

const colorClass = computed(() => {
  return props.theme === 'dark' ? 'text-fakhany-dark' : 'text-white'
})

const lineClass = computed(() => {
  return props.theme === 'dark' ? 'bg-fakhany-green' : 'bg-fakhany-gold'
})
</script>
