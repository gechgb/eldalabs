<template>
  <div class="aibot-test-page">
    <!-- Hero Section -->
    <section class="hero-section">
      <div class="hero-overlay"></div>
      <div class="floating-shapes">
        <div class="shape shape-1"></div>
        <div class="shape shape-2"></div>
        <div class="shape shape-3"></div>
      </div>
      <div class="container">
        <div class="hero-content">
          <h1 class="hero-headline">Test Our <span class="gradient-text">AI Bots</span></h1>
          <p class="hero-subheadline">Explore our AI-powered solutions for various industries</p>
        </div>
      </div>
    </section>

    <!-- Industry Selection Section -->
    <section class="section-padding">
      <div class="container">
        <h2 class="section-title">Select Your Industry</h2>
        <div class="industry-grid">
          <div class="industry-card">
            <i class="fa-solid fa-cart-shopping industry-icon"></i>
            <h3>E-commerce</h3>
            <p>Test our AI bot for e-commerce and see how it can improve customer engagement and sales.</p>
            <button class="cta-button" @click="testBot('ecommerce')">Test Bot</button>
          </div>

          <div class="industry-card">
            <i class="fa-solid fa-heart-pulse industry-icon"></i>
            <h3>Healthcare</h3>
            <p>Test our AI bot for healthcare and see how it can streamline patient management and improve healthcare outcomes.</p>
            <button class="cta-button" @click="testBot('healthcare')">Test Bot</button>
          </div>

          <div class="industry-card">
            <i class="fa-solid fa-hospital industry-icon"></i>
            <h3>Healthcare</h3>
            <p>Test our AI bot for healthcare and see how it can streamline patient care and improve medical processes.</p>
            <button class="cta-button" @click="testBot('healthcare')">Test Bot</button>
          </div>

          <div class="industry-card">
            <i class="fa-solid fa-chart-line industry-icon"></i>
            <h3>Finance</h3>
            <p>Test our AI bot for finance and see how it can automate financial processes and improve decision-making.</p>
            <button class="cta-button" @click="testBot('finance')">Test Bot</button>
          </div>

          <div class="industry-card">
            <i class="fa-solid fa-graduation-cap industry-icon"></i>
            <h3>Education</h3>
            <p>Test our AI bot for education and see how it can personalize learning experiences and improve student outcomes.</p>
            <button class="cta-button" @click="testBot('education')">Test Bot</button>
          </div>
        </div>
      </div>
    </section>
    <Footer />
  </div>
</template>

<script setup>
import { useHead } from '#imports';
import Footer from '~/components/Footer.vue';

useHead({
  title: 'Elda Labs | AI Bot Test',
  link: [
    {
      rel: 'stylesheet',
      href: 'https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css'
    }
  ]
})

const testBot = (industry) => {
  alert(`Testing AI bot for ${industry}...`);
};
</script>

<style scoped>
.aibot-test-page {
  background: var(--page-bg);
}

.hero-section {
  position: relative;
  padding: 8rem 0;
  overflow: hidden;
  background: linear-gradient(135deg, var(--primary-dark), var(--primary-color));
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
  color: var(--text-light);
}

.hero-headline {
  font-size: 3.5rem;
  margin-bottom: 1rem;
}

.gradient-text {
  background: linear-gradient(45deg, #ff6b6b, #4ecdc4);
  -webkit-background-clip: text;
  background-clip: text;
  color: transparent;
}

.hero-subheadline {
  font-size: 1.2rem;
  opacity: 0.9;
}

.section-padding {
  padding: 4rem 0;
}

.section-title {
  text-align: center;
  margin-bottom: 3rem;
  color: var(--text-primary);
}

.industry-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
  gap: 2rem;
}

.industry-card {
  background: var(--card-bg);
  padding: 2rem;
  border-radius: var(--radius-lg);
  border: 1px solid var(--border-color);
  text-align: center;
  transition: transform 0.3s ease;
}

.industry-card:hover {
  transform: translateY(-5px);
}

.industry-card h3 {
  margin-bottom: 1rem;
  color: var(--text-primary);
}

.industry-icon {
  font-size: 2.5rem;
  color: var(--primary-color);
  margin-bottom: 1rem;
  transition: transform 0.3s ease;
}

.industry-card:hover .industry-icon {
  transform: scale(1.1);
}

.industry-card p {
  color: var(--text-secondary);
  margin-bottom: 1.5rem;
}

.cta-button {
  background: var(--primary-color);
  color: var(--text-light);
  border: none;
  padding: 0.8rem 1.5rem;
  border-radius: var(--radius-full);
  cursor: pointer;
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

@media (max-width: 768px) {
  .hero-headline {
    font-size: 2.5rem;
  }

  .hero-subheadline {
    font-size: 1rem;
  }

  .industry-grid {
    grid-template-columns: 1fr;
    margin: 0 1rem;
  }
}
</style>
