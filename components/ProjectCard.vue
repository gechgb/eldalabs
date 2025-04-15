<template>
  <div class="project-card">
    <img v-if="image" :src="image" :alt="title">
    <h3>{{ title }}</h3>
    <p>{{ description }}</p>
    <a v-if="link" :href="link" target="_blank" class="view-project">View Project</a>
  </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue';

export default defineComponent({
  name: 'ProjectCard',
  props: {
    title: {
      type: String,
      required: true,
    },
    description: {
      type: String,
      required: true,
    },
    image: {
      type: String,
      required: false,
      default: '',
    },
    link: {
      type: String,
      required: false,
      default: '',
    },
  },
});
</script>

<style scoped>
.project-card {
  background: var(--neutral-100);
  border-radius: 12px;
  padding: 2.5rem;
  margin-bottom: 2rem;
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.05);
  transition: transform 0.3s ease, box-shadow 0.3s ease;
  opacity: 0;
  animation: fadeIn 0.5s ease forwards;
  border: none;
}

.project-card:hover {
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

img {
  max-width: 100%;
  height: auto;
  border-radius: 8px;
  margin-bottom: 1.5rem;
  transition: transform 0.3s ease;
}

.project-card:hover img {
  transform: scale(1.1);
}

h3 {
  color: var(--neutral-900);
  margin-bottom: 1rem;
  font-size: 1.5rem;
}

p {
  color: var(--neutral-500);
  margin-bottom: 1.5rem;
}

.view-project {
  display: inline-block;
  color: var(--accent-color);
  font-weight: 600;
  text-decoration: none;
  transition: color 0.3s ease;
}

.view-project:hover {
  color: var(--neutral-900);
  text-decoration: underline;
}
</style>
