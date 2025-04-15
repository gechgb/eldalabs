<template>
  <div>
    <!-- Hero Section -->
    <section class="hero">
      <div class="hero-background">
        <div class="gradient-blob blob-1"></div>
        <div class="gradient-blob blob-2"></div>
        <div class="gradient-blob blob-3"></div>
      </div>
      <div class="hero-overlay"></div>
      <div class="container hero-content">
        <div class="hero-text">
          <h1 class="hero-headline">We Build <span class="gradient-text">Intelligent</span> Solutions</h1>
          <p class="hero-subheadline">Helping businesses thrive in the digital age with AI-powered innovation.</p>
          <div class="hero-buttons">
            <NuxtLink to="/contact" class="cta-button primary">Get Started</NuxtLink>
            <NuxtLink to="/services" class="cta-button secondary">Explore Services</NuxtLink>
          </div>
        </div>
        <div class="hero-image-container">
          <img src="https://images.unsplash.com/photo-1581089781785-603411fa81e5?ixlib=rb-4.0.3&auto=format&fit=crop&w=1470&q=80" alt="AI Technology" class="floating-image">
        </div>
      </div>
    </section>

    <!-- Services Section -->
    <section class="section-padding services-section">
      <div class="section-background">
        <div class="gradient-circle circle-1"></div>
        <div class="gradient-circle circle-2"></div>
      </div>
      <div class="container">
        <div class="section-header">
          <h2 class="section-title">Our <span class="gradient-text">Expertise</span></h2>
          <p class="section-subtitle">Cutting-edge solutions for modern businesses</p>
        </div>
        <div class="services-grid">
          <ServiceCard 
            v-for="service in services"
            :key="service.title"
            :title="service.title"
            :description="service.description"
            :link="service.link"
          />
        </div>
      </div>
    </section>

    <!-- Projects Section -->
    <section class="section-padding projects-section">
      <div class="container">
        <div class="section-header">
          <h2 class="section-title">Success <span class="gradient-text">Stories</span></h2>
          <p class="section-subtitle">See how we've transformed businesses with intelligent solutions</p>
        </div>
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
    <section class="cta-section">
      <div class="cta-background">
        <div class="gradient-blob cta-blob-1"></div>
        <div class="gradient-blob cta-blob-2"></div>
      </div>
      <div class="container">
        <div class="cta-content">
          <h2>Ready to Transform Your Business?</h2>
          <p>Let's discuss how our intelligent solutions can help you achieve your goals.</p>
          <NuxtLink to="/contact" class="cta-button primary">Book a Strategy Call</NuxtLink>
        </div>
      </div>
    </section>

    <!-- Footer -->
    <Footer />
  </div>
</template>

<script setup>
import { useHead } from '#imports';
import ServiceCard from '~/components/ServiceCard.vue';
import ProjectCard from '~/components/ProjectCard.vue';
import Footer from '~/components/Footer.vue';

const services = [
  {
    title: 'Smart Chatbots',
    description: 'AI-powered conversational interfaces that enhance customer engagement',
    link: '/services/smart-chatbots'
  },
  {
    title: 'Digital Marketing',
    description: 'Data-driven strategies to maximize your online presence',
    link: '/services/digital-marketing'
  },
  {
    title: 'Smart SaaS',
    description: 'Scalable cloud solutions for modern business needs',
    link: '/services/smart-saas'
  },
  {
    title: 'Web Development',
    description: 'High-performance websites that drive conversions',
    link: '/services/web-development'
  },
  {
    title: 'Mobile Apps',
    description: 'Native and cross-platform mobile solutions',
    link: '/services/mobile-apps'
  }
];

const projects = [
  {
    title: 'E-commerce AI Assistant',
    description: 'Increased conversion rates by 40% for retail client',
    image: 'https://images.unsplash.com/photo-1572635148818-ef6fd45eb394?ixlib=rb-4.0.3&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=1470&q=80'
  },
  {
    title: 'Healthcare SaaS Platform',
    description: 'Streamlined patient management for 50+ clinics',
    image: 'https://images.unsplash.com/photo-1532938314519-d188a02f623d?ixlib=rb-4.0.3&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=1470&q=80'
  }
];

useHead({
  title: 'Elda Labs | Intelligence Meets Innovation',
  meta: [
    { name: 'description', content: 'Elda Labs delivers intelligent digital solutions including smart chatbots, SaaS development, web, and mobile apps to drive business growth.' }
  ]
})
</script>

<style scoped>
/* Hero Section Styles */
.hero {
  position: relative;
  color: var(--neutral-900);
  padding: 0;
  min-height: 100vh;
  display: flex;
  align-items: center;
  overflow: hidden;
}

.hero-background {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-color: var(--primary-color);
  z-index: -2;
}

.gradient-blob {
  position: absolute;
  border-radius: 50%;
  filter: blur(60px);
  opacity: 0.6;
  z-index: -1;
  animation: float 15s ease-in-out infinite;
}

.blob-1 {
  width: 500px;
  height: 500px;
  background: radial-gradient(circle, var(--accent-color) 0%, rgba(108, 99, 255, 0) 70%);
  top: -100px;
  right: -100px;
  animation-delay: 0s;
}

.blob-2 {
  width: 600px;
  height: 600px;
  background: radial-gradient(circle, var(--secondary-color) 0%, rgba(79, 172, 254, 0) 70%);
  bottom: -150px;
  left: -100px;
  animation-delay: -5s;
}

.blob-3 {
  width: 300px;
  height: 300px;
  background: radial-gradient(circle, var(--success-color) 0%, rgba(16, 185, 129, 0) 70%);
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  animation-delay: -10s;
}

.hero-overlay {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background: rgba(30, 30, 47, 0.3);
  backdrop-filter: blur(5px);
  z-index: -1;
}

.hero-content {
  display: flex;
  align-items: center;
  justify-content: space-between;
  padding: 6rem 2rem;
  flex-wrap: wrap;
}

.hero-text {
  flex: 1;
  min-width: 300px;
  max-width: 600px;
  text-align: left;
  animation: slideUp 1s ease forwards;
}

.hero-image-container {
  flex: 1;
  min-width: 300px;
  display: flex;
  justify-content: center;
  align-items: center;
}

.floating-image {
  max-width: 100%;
  height: auto;
  border-radius: var(--radius-lg);
  box-shadow: 0 20px 40px rgba(0, 0, 0, 0.2);
  animation: float 6s ease-in-out infinite;
}

.gradient-text {
  background: linear-gradient(135deg, var(--accent-color), var(--secondary-color));
  -webkit-background-clip: text;
  background-clip: text;
  color: transparent;
  display: inline;
}

.hero-headline {
  font-size: clamp(2.5rem, 5vw, 4.5rem);
  font-weight: 700;
  line-height: 1.1;
  margin-bottom: 1.5rem;
}

.hero-subheadline {
  font-size: clamp(1.25rem, 2vw, 1.75rem);
  font-weight: 400;
  color: var(--neutral-500);
  margin-bottom: 2.5rem;
}

.hero-buttons {
  display: flex;
  gap: 1rem;
  flex-wrap: wrap;
}

.cta-button {
  display: inline-block;
  padding: 1rem 2rem;
  border-radius: var(--radius-md);
  font-weight: 600;
  text-decoration: none;
  transition: all 0.3s ease;
  position: relative;
  overflow: hidden;
  z-index: 1;
}

.cta-button.primary {
  background: linear-gradient(135deg, var(--accent-color), var(--secondary-color));
  color: var(--neutral-900);
  box-shadow: 0 4px 15px rgba(108, 99, 255, 0.3);
}

.cta-button.secondary {
  background: rgba(255, 255, 255, 0.1);
  backdrop-filter: blur(10px);
  border: 1px solid rgba(255, 255, 255, 0.2);
  color: var(--neutral-800);
}

.cta-button:hover {
  transform: translateY(-3px);
}

.cta-button.primary:hover {
  box-shadow: 0 6px 20px rgba(108, 99, 255, 0.4);
}

.cta-button.secondary:hover {
  background: rgba(255, 255, 255, 0.2);
}

/* Services Section Styles */
.section-padding {
  padding: 8rem 0;
  position: relative;
  overflow: hidden;
}

.section-background {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  z-index: -1;
}

.gradient-circle {
  position: absolute;
  border-radius: 50%;
  filter: blur(80px);
  opacity: 0.1;
}

.circle-1 {
  width: 800px;
  height: 800px;
  background: var(--accent-color);
  top: -400px;
  right: -200px;
}

.circle-2 {
  width: 600px;
  height: 600px;
  background: var(--secondary-color);
  bottom: -300px;
  left: -100px;
}

.section-header {
  text-align: center;
  margin-bottom: 4rem;
}

.section-title {
  font-size: clamp(2rem, 4vw, 3rem);
  margin-bottom: 1rem;
}

.section-subtitle {
  font-size: 1.25rem;
  color: var(--neutral-500);
  max-width: 600px;
  margin: 0 auto;
}

.services-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
  gap: 2rem;
}

/* Projects Section Styles */
.projects-section {
  background-color: rgba(30, 30, 47, 0.03);
}

.projects-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
  gap: 3rem;
}

/* CTA Section */
.cta-section {
  position: relative;
  padding: 6rem 0;
  background-color: var(--primary-color);
  overflow: hidden;
}

.cta-background {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  z-index: 0;
}

.cta-blob-1 {
  width: 400px;
  height: 400px;
  background: radial-gradient(circle, var(--accent-color) 0%, rgba(108, 99, 255, 0) 70%);
  top: -100px;
  right: 10%;
}

.cta-blob-2 {
  width: 300px;
  height: 300px;
  background: radial-gradient(circle, var(--secondary-color) 0%, rgba(79, 172, 254, 0) 70%);
  bottom: -50px;
  left: 10%;
}

.cta-content {
  position: relative;
  z-index: 1;
  text-align: center;
  max-width: 800px;
  margin: 0 auto;
  color: var(--neutral-900);
}

.cta-content h2 {
  font-size: clamp(2rem, 4vw, 3rem);
  margin-bottom: 1.5rem;
}

.cta-content p {
  font-size: 1.25rem;
  margin-bottom: 2rem;
  color: var(--neutral-500);
}

/* Animations */
@keyframes float {
  0% {
    transform: translateY(0);
  }
  50% {
    transform: translateY(-20px);
  }
  100% {
    transform: translateY(0);
  }
}

@keyframes slideUp {
  from {
    opacity: 0;
    transform: translateY(30px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

/* Responsive Adjustments */
@media (max-width: 768px) {
  .hero-content {
    flex-direction: column;
    text-align: center;
  }
  
  .hero-text {
    order: 2;
    text-align: center;
  }
  
  .hero-image-container {
    order: 1;
    margin-bottom: 2rem;
  }
  
  .hero-buttons {
    justify-content: center;
  }
}
</style>
