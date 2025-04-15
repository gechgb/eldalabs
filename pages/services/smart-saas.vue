<template>
  <div class="section-padding">
    <div class="container">
      <div class="service-header">
        <img src="https://images.unsplash.com/photo-1551434678-e076c223a692?w=1200&auto=format&fit=crop&q=80" alt="Smart SaaS Solutions" class="hero-image">
        <h1>Smart SaaS Solutions</h1>
        <p class="lead">Develop scalable and intelligent Software-as-a-Service products tailored to your business needs.</p>
      </div>
      
      <div class="features-grid">
        <div class="feature-card">
          <img src="https://images.unsplash.com/photo-1544197150-b99a580bb7a8?w=600&auto=format&fit=crop&q=80" alt="Cloud Solutions" class="feature-image">
          <h3>Cloud Solutions</h3>
          <p>Scalable infrastructure for growing businesses.</p>
        </div>
        <div class="feature-card">
          <img src="https://images.unsplash.com/photo-1551434908-b3c77beb9b5d?w=600&auto=format&fit=crop&q=80" alt="Data Analytics" class="feature-image">
          <h3>Data Analytics</h3>
          <p>Powerful insights from your business data.</p>
        </div>
        <div class="feature-card">
          <img src="https://images.unsplash.com/photo-1558494949-ef010cbdcc31?w=600&auto=format&fit=crop&q=80" alt="API Integration" class="feature-image">
          <h3>API Integration</h3>
          <p>Seamless connections with your existing tools.</p>
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
  max-width: 800px;
  margin: 0 auto 2rem;
  color: var(--neutral-600);
}

.features-grid {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
  gap: 2rem;
  margin-top: 3rem;
}

.feature-card {
  background: rgba(255, 255, 255, 0.05);
  border-radius: var(--radius-md);
  padding: 1.5rem;
  text-align: center;
  transition: transform 0.3s ease;
  border: 1px solid rgba(255, 255, 255, 0.1);
}

.feature-card:hover {
  transform: translateY(-5px);
}

.feature-image {
  width: 100%;
  height: 200px;
  object-fit: cover;
  border-radius: var(--radius-sm);
  margin-bottom: 1rem;
}
</style>
