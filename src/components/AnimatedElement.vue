<template>
  <div ref="target" :class="[computedClasses, transitionClass]" :style="computedStyle">
    <slot />
  </div>
</template>

<script setup>
import { ref, computed, onMounted, onUnmounted } from 'vue'

const props = defineProps({
  direction: {
    type: String,
    default: 'up', // 'up', 'down', 'left', 'right', 'none'
  },
  trigger: {
    type: String,
    default: 'scroll', // 'scroll', 'mount'
  },
  delay: {
    type: Number,
    default: 0,
  },
  duration: {
    type: Number,
    default: 800,
  }
})

const target = ref(null)
const isVisible = ref(false)

const computedClasses = computed(() => {
  if (isVisible.value) {
    return 'opacity-100 translate-x-0 translate-y-0'
  }
  
  let classes = 'opacity-0 '
  switch (props.direction) {
    case 'up': classes += 'translate-y-16'; break;
    case 'down': classes += '-translate-y-16'; break;
    // In RTL, left is visually the right side sometimes depending on context, 
    // but translate-x is physical.
    // -translate-x goes to physical left.
    case 'left': classes += '-translate-x-16'; break; 
    case 'right': classes += 'translate-x-16'; break;
  }
  return classes
})

const transitionClass = computed(() => {
  return 'transition-all ease-out'
})

const computedStyle = computed(() => {
  return {
    transitionDuration: `${props.duration}ms`,
    transitionDelay: `${props.delay}ms`
  }
})

onMounted(() => {
  if (props.trigger === 'mount') {
    // Add a tiny timeout so the DOM finishes painting before we apply the visible class
    setTimeout(() => {
      isVisible.value = true
    }, 50)
  } else if (props.trigger === 'scroll') {
    const observer = new IntersectionObserver((entries) => {
      entries.forEach(entry => {
        if (entry.isIntersecting) {
          isVisible.value = true
          observer.unobserve(entry.target)
        }
      })
    }, {
      threshold: 0.1,
      rootMargin: '0px 0px -50px 0px'
    })
    
    if (target.value) {
      observer.observe(target.value)
    }
    
    onUnmounted(() => {
      observer.disconnect()
    })
  }
})
</script>
