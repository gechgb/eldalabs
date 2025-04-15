<template>
  <div class="projects-page">
    <!-- Hero Section -->
    <section class="hero-section projects-hero">
      <div class="hero-background">
        <div class="gradient-blob blob-1"></div>
        <div class="gradient-blob blob-2"></div>
        <div class="gradient-blob blob-3"></div>
      </div>
      <div class="hero-overlay"></div>
      <div class="container">
        <div class="hero-content">
          <div class="hero-text">
            <h1 class="hero-headline">Our <span class="gradient-text">Projects</span></h1>
            <p class="hero-subheadline">Discover how we transform ideas into impactful digital solutions</p>
          </div>
        </div>
      </div>
    </section>

    <!-- Project Categories Section -->
    <section class="section-padding categories-section">
      <div class="container">
        <div class="section-header">
          <h2 class="section-title">Browse by <span class="gradient-text">Category</span></h2>
          <div class="title-underline"></div>
        </div>
        <div class="category-list">
          <button class="category-button active">All</button>
          <button class="category-button">AI</button>
          <button class="category-button">SaaS</button>
          <button class="category-button">Web</button>
          <button class="category-button">Mobile</button>
          <button class="category-button">Marketing</button>
        </div>
      </div>
    </section>

    <!-- Project Grid Section -->
    <section class="section-padding projects-grid-section">
      <div class="container">
        <div class="projects-grid">
          <ProjectCard 
            v-for="project in projects"
            :key="project.title"
            :title="project.title"
            :description="project.description"
            :image="project.image"
          />
        </div>
      </div>
    </section>

    <!-- Call to Action Section -->
    <section class="section-padding cta-section">
      <div class="container">
        <div class="cta-content">
          <h2 class="cta-title">Ready to Build Something <span class="gradient-text">Amazing?</span></h2>
          <p class="cta-description">Let's collaborate to bring your vision to life with our expertise in cutting-edge technology</p>
          <NuxtLink to="/contact" class="cta-button">Start a Project</NuxtLink>
        </div>
      </div>
    </section>
    
    <!-- Footer Section -->
    <Footer />
  </div>
</template>

<script setup>
import { useHead } from '#imports';
import ProjectCard from '~/components/ProjectCard.vue';
import Footer from '~/components/Footer.vue';

const projects = [
  {
    title: 'AI-Powered Customer Service',
    description: 'Revolutionizing support with intelligent automation',
    image: 'https://images.unsplash.com/photo-1607252650355-f5a35c1549e6?w=1470&q=80'
  },
  {
    title: 'Healthcare Analytics Platform',
    description: 'Data-driven insights for better patient care',
    image: 'https://images.unsplash.com/photo-1588702547954-49e99d7cfe83?w=1470&q=80'
  },
  {
    title: 'Smart City Dashboard',
    description: 'Real-time monitoring for urban efficiency',
    image: 'https://images.unsplash.com/photo-1573164713714-d95e436ab8d6?w=1470&q=80'
  },
  {
    title: 'Fintech Mobile App',
    description: 'Secure and intuitive financial management',
    image: 'https://images.unsplash.com/photo-1563986768609-322da13575f3?w=1470&q=80'
  }
];

useHead({
  title: 'Elda Labs | Projects'
});
</script>

<style scoped>
.projects-page {
  background: var(--page-bg);
}

/* Hero Section */
.hero-section {
  position: relative;
  padding: 8rem 0;
  overflow: hidden;
  background: linear-gradient(135deg, var(--primary-dark), var(--primary-color));
}

.hero-headline {
  font-size: clamp(2.5rem, 5vw, 4rem);
  font-weight: 700;
  margin-bottom: 1.5rem;
  color: var(--text-light);
  line-height: 1.2;
}

.hero-subheadline {
  font-size: clamp(1.1rem, 2vw, 1.5rem);
  color: var(--text-light-muted);
  max-width: 600px;
  margin: 0 auto;
  line-height: 1.6;
}

.hero-overlay {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background: radial-gradient(circle at 50% 50%, rgba(255,255,255,0.1) 0%, rgba(0,0,0,0.3) 100%);
}

.floating-shapes {
  position: absolute;
  width: 100%;
  height: 100%;
  top: 0;
  left: 0;
}

.shape {
  position: absolute;
  border-radius: 50%;
  background: rgba(255,255,255,0.1);
  animation: float 20s infinite;
}

.shape-1 {
  width: 300px;
  height: 300px;
  top: -150px;
  right: -150px;
}

.shape-2 {
  width: 200px;
  height: 200px;
  bottom: -100px;
  left: -100px;
}

.shape-3 {
  width: 150px;
  height: 150px;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
}

.hero-content {
  position: relative;
  z-index: 1;
  text-align: center;
  max-width: 800px;
  margin: 0 auto;
}

.hero-headline {
  font-size: 4rem;
  font-weight: 700;
  margin-bottom: 1.5rem;
  color: var(--text-light);
}

.hero-subheadline {
  font-size: 1.5rem;
  color: var(--text-light-muted);
}

/* Categories Section */
.categories-section {
  position: relative;
}

.category-list {
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
  gap: 1rem;
  margin-top: 2rem;
}

.category-button {
  padding: 0.75rem 1.5rem;
  border: none;
  border-radius: 50px;
  background: var(--card-bg);
  color: var(--text-primary);
  font-weight: 500;
  cursor: pointer;
  transition: all 0.3s ease;
  border: 1px solid var(--border-color);
}

.category-button:hover,
.category-button.active {
  background: var(--primary-color);
  color: var(--text-light);
  transform: translateY(-2px);
}

/* Projects Grid */
.projects-grid {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
  gap: 2rem;
  margin-top: 3rem;
}

/* CTA Section */
.cta-section {
  background: linear-gradient(135deg, var(--primary-dark), var(--primary-color));
  color: var(--text-light);
  text-align: center;
  border-radius: var(--radius-lg);
  margin: 4rem 0;
}

.cta-content {
  max-width: 600px;
  margin: 0 auto;
}

.cta-title {
  font-size: 2.5rem;
  margin-bottom: 1.5rem;
}

.cta-description {
  font-size: 1.25rem;
  color: var(--text-light-muted);
  margin-bottom: 2rem;
}

.cta-button {
  display: inline-block;
  padding: 1rem 2rem;
  background: var(--accent-color);
  color: var(--text-light);
  border-radius: var(--radius-full);
  font-weight: 500;
  text-decoration: none;
  transition: all 0.3s ease;
}

.cta-button:hover {
  transform: translateY(-2px);
  box-shadow: 0 4px 12px rgba(0,0,0,0.1);
}

@keyframes float {
  0%, 100% { transform: translate(0, 0); }
  25% { transform: translate(10px, -10px); }
  50% { transform: translate(-5px, 5px); }
  75% { transform: translate(5px, 10px); }
}
</style>
