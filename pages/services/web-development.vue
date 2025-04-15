<template>
  <div class="section-padding">
    <div class="container">
      <div class="service-header">
        <img src="https://images.unsplash.com/photo-1498050108023-c5249f4df085?w=1200&auto=format&fit=crop&q=80" alt="Web Development" class="hero-image">
        <h1>Web Development</h1>
        <p class="lead">Crafting beautiful, high-performance websites and web applications that drive results.</p>
      </div>
      
      <div class="features-grid">
        <div class="feature-card">
          <img src="https://images.unsplash.com/photo-1507238691740-187a5b1d37b8?w=600&auto=format&fit=crop&q=80" alt="Responsive Design" class="feature-image">
          <h3>Responsive Design</h3>
          <p>Websites that look and work perfectly on all devices.</p>
        </div>
        <div class="feature-card">
          <img src="https://images.unsplash.com/photo-1460925895917-afdab827c52f?w=600&auto=format&fit=crop&q=80" alt="Performance" class="feature-image">
          <h3>Lightning Fast</h3>
          <p>Optimized for speed and performance.</p>
        </div>
        <div class="feature-card">
          <img src="https://images.unsplash.com/photo-1504639725590-34d0984388bd?w=600&auto=format&fit=crop&q=80" alt="SEO" class="feature-image">
          <h3>SEO Ready</h3>
          <p>Built with search engines in mind.</p>
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
