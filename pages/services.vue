<template>
  <div class="services-page">
    <!-- Hero Section -->
    <section class="hero-section services-hero">
      <div class="hero-background">
        <div class="gradient-blob blob-1"></div>
        <div class="gradient-blob blob-2"></div>
        <div class="gradient-blob blob-3"></div>
      </div>
      <div class="hero-overlay"></div>
      <div class="container">
        <div class="hero-content">
          <div class="hero-text">
            <h1 class="hero-headline">Our <span class="gradient-text">Services</span></h1>
            <p class="hero-subheadline">Leveraging artificial intelligence and cutting-edge technology to provide innovative, practical, and results-driven solutions.</p>
          </div>
        </div>
      </div>
    </section>

    <!-- Services Section -->
    <section class="section-padding services-section">
      <div class="container">
        <div class="section-header">
          <h2 class="section-title">What We <span class="gradient-text">Offer</span></h2>
          <div class="title-underline"></div>
          <p class="section-subtitle">Explore our comprehensive range of services designed to propel your business forward in the digital age</p>
        </div>
        <div class="service-categories">
      <ServiceCard
        title="AI-Powered Software Development"
        description="Develop custom software solutions infused with artificial intelligence to automate processes, gain insights, and enhance user experiences."
        :features="[
          'Machine Learning Applications',
          'Predictive Analytics',
          'Natural Language Processing',
          'Computer Vision'
        ]"
        image="https://images.unsplash.com/photo-1555066931-4365d14bab8c?ixlib=rb-4.0.3&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=1470&q=80"
      />

      <ServiceCard
        title="Smart Chatbots & Virtual Assistants"
        description="Implement intelligent conversational AI solutions that enhance customer engagement and streamline operations."
        :features="[
          'Custom NLP Integration',
          '24/7 Automated Support',
          'Multi-channel Deployment',
          'Continuous Learning Algorithms'
        ]"
        :to="{ name: 'services-smart-chatbots' }"
        image="https://images.unsplash.com/photo-1517245412977-9aa35e080d8e?ixlib=rb-4.0.3&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=1470&q=80"
      />
      <ServiceCard
        title="Smart SaaS Solutions"
        description="Utilize our expertise to create scalable and intelligent SaaS platforms that address specific business needs and provide ongoing value."
        :features="[
          'Cloud-Based Applications',
          'Subscription Services',
          'API Integrations',
          'Data Analytics Dashboards'
        ]"
        image="https://images.unsplash.com/photo-1505373467456-685db550cfcc?ixlib=rb-4.0.3&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=1470&q=80"
      />
      <ServiceCard
        title="Impactful Digital Branding"
        description="Craft a strong and memorable brand identity that resonates with your target audience and sets you apart in the digital landscape."
        :features="[
          'Brand Strategy & Design',
          'UI/UX Design',
          'Digital Marketing',
          'Content Creation'
        ]"
        image="https://images.unsplash.com/photo-1505373876842-690974a046b1?ixlib=rb-4.0.3&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=1470&q=80"
      />
    </div>
      </div>
    </section>

    <!-- Contact Us Section -->
    <section class="section-padding contact-section">
      <div class="container">
        <div class="section-header">
          <h2 class="section-title">Ready to <span class="gradient-text">Get Started?</span></h2>
          <div class="title-underline"></div>
          <p class="section-subtitle">Let's discuss how our services can transform your business</p>
        </div>
        <div class="contact-cta">
          <NuxtLink to="/contact" class="cta-button">Book Strategy Call</NuxtLink>
        </div>
      </div>
    </section>
    <Footer />
  </div>
</template>

<script setup>
import ServiceCard from '~/components/ServiceCard.vue';
import Footer from '~/components/Footer.vue';

useHead({
  title: 'Elda Labs | Services'
})
</script>

<style scoped>
/* Hero Section Styles */
.services-hero {
  position: relative;
  padding: 12rem 0 8rem;
  overflow: hidden;
}

.hero-section {
  position: relative;
  padding: 8rem 0;
  overflow: hidden;
  background: var(--page-bg);
}

.hero-background {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  overflow: hidden;
  z-index: 1;
}

.gradient-blob {
  position: absolute;
  border-radius: 50%;
  filter: blur(40px);
  opacity: 0.6;
}

.blob-1 {
  width: 400px;
  height: 400px;
  background: linear-gradient(135deg, var(--primary-color), var(--accent-color));
  top: -100px;
  right: -100px;
}

.blob-2 {
  width: 300px;
  height: 300px;
  background: linear-gradient(135deg, var(--secondary-color), var(--primary-color));
  bottom: -50px;
  left: -50px;
}

.blob-3 {
  width: 200px;
  height: 200px;
  background: linear-gradient(135deg, var(--accent-color), var(--secondary-color));
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
}

.hero-overlay {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background: rgba(0, 0, 0, 0.1);
  z-index: 2;
}

.hero-content {
  position: relative;
  z-index: 3;
  text-align: center;
}

.hero-text {
  max-width: 800px;
  margin: 0 auto;
}

.hero-headline {
  font-size: 4rem;
  font-weight: 700;
  margin-bottom: 1.5rem;
  color: var(--text-primary);
  line-height: 1.2;
}

.hero-subheadline {
  font-size: 1.25rem;
  color: var(--text-secondary);
  margin-bottom: 2rem;
  line-height: 1.6;
}

.gradient-text {
  background: linear-gradient(135deg, var(--primary-color), var(--accent-color));
  -webkit-background-clip: text;
  background-clip: text;
  color: transparent;
  display: inline-block;
}

@media (max-width: 768px) {
  .hero-headline {
    font-size: 2.5rem;
  }

  .hero-subheadline {
    font-size: 1.1rem;
  }
}
.hero-overlay {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background: linear-gradient(135deg, rgba(26, 27, 75, 0.9), rgba(108, 99, 255, 0.8));
  z-index: -1;
}

.floating-shapes .shape {
  position: absolute;
  border-radius: 50%;
  filter: blur(40px);
  opacity: 0.4;
  z-index: -1;
}

.shape-1 {
  width: 300px;
  height: 300px;
  background: var(--accent-color);
  top: -100px;
  right: -100px;
  animation: float 15s ease-in-out infinite alternate;
}

.shape-2 {
  width: 200px;
  height: 200px;
  background: var(--secondary-color);
  bottom: -50px;
  left: -50px;
  animation: float 18s ease-in-out infinite alternate-reverse;
}

.shape-3 {
  width: 150px;
  height: 150px;
  background: var(--primary-color);
  top: 40%;
  left: 30%;
  animation: float 12s ease-in-out infinite;
}

@keyframes float {
  0% {
    transform: translate(0, 0) rotate(0deg);
  }
  50% {
    transform: translate(20px, 20px) rotate(5deg);
  }
  100% {
    transform: translate(-20px, 10px) rotate(-5deg);
  }
}

.hero-content {
  text-align: center;
  max-width: 800px;
  margin: 0 auto;
  z-index: 2;
}

.hero-headline {
  font-size: 4rem;
  font-weight: 700;
  margin-bottom: 1.5rem;
  line-height: 1.2;
}

.hero-subheadline {
  font-size: 1.5rem;
  margin-bottom: 2.5rem;
  color: var(--neutral-800);
  max-width: 700px;
  margin-left: auto;
  margin-right: auto;
}

/* Section Styles */
.section-padding {
  padding: 6rem 0;
}

.container {
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 20px;
}

.section-header {
  text-align: center;
  margin-bottom: 4rem;
}

.section-title {
  font-size: 3rem;
  font-weight: 700;
  margin-bottom: 1rem;
}

.section-subtitle {
  font-size: 1.25rem;
  color: var(--neutral-500);
  max-width: 700px;
  margin: 1rem auto 0;
}

.title-underline {
  height: 4px;
  width: 80px;
  background: linear-gradient(90deg, var(--accent-color), var(--secondary-color));
  margin: 1rem auto;
  border-radius: 2px;
}

.gradient-text {
  background: linear-gradient(135deg, var(--accent-color), var(--secondary-color));
  -webkit-background-clip: text;
  background-clip: text;
  color: transparent;
}

/* Services Section Styles */
.service-categories {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
  gap: 30px;
}

/* Contact Section Styles */
.contact-section {
  text-align: center;
}

.contact-cta {
  margin-top: 3rem;
}

.cta-button {
  display: inline-block;
  background: linear-gradient(135deg, var(--accent-color), var(--secondary-color));
  color: var(--neutral-900);
  padding: 1rem 2rem;
  border-radius: var(--radius-md);
  font-weight: 600;
  text-decoration: none;
  transition: all 0.3s ease;
  border: none;
  cursor: pointer;
  box-shadow: 0 4px 15px rgba(108, 99, 255, 0.3);
}

.cta-button:hover {
  transform: translateY(-3px);
  box-shadow: 0 8px 25px rgba(108, 99, 255, 0.5);
}

/* Responsive Styles */
@media (max-width: 992px) {
  .hero-headline {
    font-size: 3rem;
  }
}

@media (max-width: 768px) {
  .hero-headline {
    font-size: 2.5rem;
  }
  
  .hero-subheadline {
    font-size: 1.25rem;
  }
  
  .section-title {
    font-size: 2.5rem;
  }
}

@media (max-width: 480px) {
  .hero-headline {
    font-size: 2rem;
  }
  
  .section-title {
    font-size: 2rem;
  }
  
  .service-categories {
    grid-template-columns: 1fr;
  }
}
</style>
