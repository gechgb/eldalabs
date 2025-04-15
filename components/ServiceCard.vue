<template>
  <div class="service-card">
    <div v-if="image" class="service-image">
      <img :src="image" :alt="title">
    </div>
    <h3>{{ title }}</h3>
    <p>{{ description }}</p>
    <ul v-if="features && features.length" class="feature-list">
      <li v-for="(feature, index) in features" :key="index">{{ feature }}</li>
    </ul>
    <div class="service-link">
      <NuxtLink v-if="to" :to="to" class="learn-more">Learn More</NuxtLink>
      <a v-else-if="link" :href="link" class="learn-more">Learn More</a>
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue';

export default defineComponent({
  name: 'ServiceCard',
  props: {
    title: {
      type: String,
      required: true,
    },
    description: {
      type: String,
      required: true,
    },
    link: {
      type: String,
      required: false,
      default: '',
    },
    to: {
      type: Object,
      required: false,
      default: null,
    },
    features: {
      type: Array,
      required: false,
      default: () => [],
    },
    image: {
      type: String,
      required: false,
      default: '',
    },
  },
});
</script>

<style scoped>
.service-card {
  background: rgba(30, 30, 47, 0.7);
  backdrop-filter: blur(12px);
  -webkit-backdrop-filter: blur(12px);
  border-radius: var(--radius-lg);
  border: 1px solid rgba(255, 255, 255, 0.1);
  padding: 2.5rem;
  margin-bottom: 2rem;
  box-shadow: 0 8px 32px rgba(0, 0, 0, 0.1);
  transition: all 0.4s ease;
  opacity: 0;
  animation: fadeIn 0.5s ease forwards;
}

.service-card:hover {
  transform: translateY(-5px);
  box-shadow: 0 8px 16px rgba(0, 0, 0, 0.1);
}

@keyframes fadeIn {
  from {
    opacity: 0;
    transform: translateY(20px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

.service-image {
  margin-bottom: 1.5rem;
  overflow: hidden;
  border-radius: 8px;
}

.service-image img {
  width: 100%;
  height: auto;
  transition: transform 0.3s ease;
}

.service-image:hover img {
  transform: scale(1.1);
}

h3 {
  font-size: 1.5rem;
  margin-bottom: 1rem;
  color: var(--neutral-900);
  background: linear-gradient(135deg, var(--accent-color), var(--secondary-color));
  -webkit-background-clip: text;
  background-clip: text;
  color: transparent;
  font-weight: 700;
}

p {
  color: var(--neutral-500);
  margin-bottom: 1.5rem;
}

.feature-list {
  margin-bottom: 1.5rem;
  padding-left: 1.5rem;
}

.feature-list li {
  color: var(--neutral-500);
  margin-bottom: 0.5rem;
}

.learn-more {
  display: inline-block;
  padding: 0.75rem 1.5rem;
  background: linear-gradient(135deg, var(--accent-color), var(--secondary-color));
  color: var(--neutral-900);
  text-decoration: none;
  border-radius: var(--radius-md);
  font-weight: 600;
  transition: all 0.3s ease;
  box-shadow: 0 4px 15px rgba(108, 99, 255, 0.3);
}

.learn-more:hover {
  transform: translateY(-3px);
  box-shadow: 0 8px 25px rgba(108, 99, 255, 0.5);
}
</style>
