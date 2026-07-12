<template>
  <button
    v-motion
    :initial="animated ? { scale: 1 } : {}"
    :hovered="animated ? { scale: 1.05 } : {}"
    :tapped="animated ? { scale: 0.95 } : {}"
    :class="[
      'font-semibold py-2 px-6 rounded-full transition-all duration-300 shadow-md text-center cursor-pointer select-none outline-none focus:ring-2 focus:ring-fakhany-gold/50',
      variantClass,
      customClass
    ]"
    @click="$emit('click')"
  >
    <slot></slot>
  </button>
</template>

<script setup>
import { computed } from 'vue'

const props = defineProps({
  variant: {
    type: String,
    default: 'primary' // 'primary' (green) | 'outline' (gold border) | 'gold' (gold solid)
  },
  animated: {
    type: Boolean,
    default: true
  },
  customClass: {
    type: String,
    default: ''
  }
})

const emit = defineEmits(['click'])

const variantClass = computed(() => {
  switch (props.variant) {
    case 'primary':
      // The FAKHANY delivery button green: leafy green
      return 'bg-fakhany-green hover:bg-fakhany-greenHover text-white shadow-fakhany-green/20'
    case 'outline':
      // The FAKHANY "تسوق الآن" button: green fill with gold border as in design, or transparent gold border.
      // Looking closely at "تسوق الآن" in page.jpeg: it is green background with a bright gold border!
      return 'border-2 border-fakhany-gold bg-fakhany-green text-white hover:bg-fakhany-greenHover shadow-fakhany-gold/20'
    case 'gold':
      // Golden gradient button for forms/newsletter
      return 'gold-gradient-bg text-fakhany-dark font-bold hover:opacity-90 shadow-fakhany-gold/30'
    default:
      return 'bg-gray-700 hover:bg-gray-600 text-white'
  }
})
</script>
