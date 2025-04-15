<template>
  <div class="section-padding">
    <div class="container">
      <div class="service-header">
        <img src="https://images.unsplash.com/photo-1531746790731-6c087fecd65a?w=1200&auto=format&fit=crop&q=80" alt="AI Chatbot" class="hero-image">
        <h1>Smart Chatbots</h1>
        <p class="lead">Engage your customers 24/7 with intelligent, AI-powered chatbots.</p>
      </div>
      
      <div class="features-grid">
        <div class="feature-card">
          <img src="https://images.unsplash.com/photo-1535378620166-273708d44e4c?w=600&auto=format&fit=crop&q=80" alt="24/7 Support" class="feature-image">
          <h3>24/7 Support</h3>
          <p>Always available to help your customers.</p>
        </div>
        <div class="feature-card">
          <img src="https://images.unsplash.com/photo-1596526131083-e8c633c948d2?w=600&auto=format&fit=crop&q=80" alt="AI Learning" class="feature-image">
          <h3>AI Learning</h3>
          <p>Continuously improving responses.</p>
        </div>
        <div class="feature-card">
          <img src="https://images.unsplash.com/photo-1516321318423-f06f85e504b3?w=600&auto=format&fit=crop&q=80" alt="Analytics" class="feature-image">
          <h3>Smart Analytics</h3>
          <p>Insights from every conversation.</p>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
// Add necessary script logic if needed later
</script>

<style scoped>
.service-header {
  text-align: center;
  margin-bottom: 4rem;
}

.hero-image {
  width: 100%;
  max-width: 1000px;
  height: auto;
  border-radius: var(--radius-lg);
  margin-bottom: 2rem;
  box-shadow: var(--shadow-lg);
}

.lead {
  font-size: 1.25rem;
  color: var(--neutral-500);
  max-width: 800px;
  margin: 1rem auto;
}

.features-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
  gap: 2rem;
  margin-top: 3rem;
}

.feature-card {
  background: var(--neutral-100);
  border-radius: var(--radius-lg);
  padding: 1.5rem;
  text-align: center;
  transition: transform 0.3s ease;
}

.feature-card:hover {
  transform: translateY(-5px);
}

.feature-image {
  width: 100%;
  height: 200px;
  object-fit: cover;
  border-radius: var(--radius-md);
  margin-bottom: 1.5rem;
}

.feature-card h3 {
  margin: 1rem 0;
  color: var(--neutral-900);
}

.feature-card p {
  color: var(--neutral-500);
}
</style>
