<template>
  <svg class="team-avatar" :width="size" :height="size" viewBox="0 0 200 200" xmlns="http://www.w3.org/2000/svg">
    <!-- Background Circle -->
    <circle cx="100" cy="100" r="98" :fill="bgColor" />
    
    <!-- Decorative Elements -->
    <path
      :d="`M40,${100 + variation} Q100,${150 + variation} 160,${100 + variation}`"
      :stroke="accentColor"
      stroke-width="2"
      fill="none"
      opacity="0.5"
    />
    <circle
      :cx="75 + variation"
      :cy="75 + variation"
      r="8"
      :fill="accentColor"
      opacity="0.7"
    />
    <circle
      :cx="125 - variation"
      :cy="75 + variation"
      r="8"
      :fill="accentColor"
      opacity="0.7"
    />
    
    <!-- Gradient Overlay -->
    <defs>
      <linearGradient id="avatarGradient" x1="0%" y1="0%" x2="100%" y2="100%">
        <stop offset="0%" :stop-color="gradientStart" stop-opacity="0.2" />
        <stop offset="100%" :stop-color="gradientEnd" stop-opacity="0.1" />
      </linearGradient>
    </defs>
    <circle cx="100" cy="100" r="98" fill="url(#avatarGradient)" />
  </svg>
</template>

<script setup>
import { computed } from 'vue';

const props = defineProps({
  size: {
    type: Number,
    default: 200
  },
  bgColor: {
    type: String,
    default: '#1A1B4B' // var(--primary-color)
  },
  accentColor: {
    type: String,
    default: '#6C63FF' // var(--accent-color)
  },
  gradientStart: {
    type: String,
    default: '#4FACFE' // var(--secondary-color)
  },
  gradientEnd: {
    type: String,
    default: '#6C63FF' // var(--accent-color)
  },
  seed: {
    type: Number,
    default: () => Math.random() * 100
  }
});

const variation = computed(() => {
  return Math.sin(props.seed) * 10;
});
</script>

<style scoped>
.team-avatar {
  transition: transform 0.3s ease;
}

.team-avatar:hover {
  transform: scale(1.05);
}
</style>