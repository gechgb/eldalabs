<template>
  <div class="section-padding">
    <div class="container">
      <div class="service-header">
        <img src="https://images.unsplash.com/photo-1432888498266-38ffec3eaf0a?w=1200&auto=format&fit=crop&q=80" alt="Digital Marketing" class="hero-image">
        <h1>Digital Marketing</h1>
        <p class="lead">Amplify your brand's reach and drive growth with data-driven digital marketing strategies.</p>
      </div>
      
      <div class="features-grid">
        <div class="feature-card">
          <img src="https://images.unsplash.com/photo-1533750516457-a7f992034fec?w=600&auto=format&fit=crop&q=80" alt="SEO" class="feature-image">
          <h3>Search Engine Optimization</h3>
          <p>Improve visibility and organic traffic.</p>
        </div>
        <div class="feature-card">
          <img src="https://images.unsplash.com/photo-1611926653458-09294b3142bf?w=600&auto=format&fit=crop&q=80" alt="Social Media" class="feature-image">
          <h3>Social Media Marketing</h3>
          <p>Engage audiences where they spend time.</p>
        </div>
        <div class="feature-card">
          <img src="https://images.unsplash.com/photo-1590845947670-c009801ffa74?w=600&auto=format&fit=crop&q=80" alt="Analytics" class="feature-image">
          <h3>Data Analytics</h3>
          <p>Make decisions based on real insights.</p>
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
