<template>
  <div class="section-padding">
    <div class="container">
      <div class="service-header">
        <img src="https://images.unsplash.com/photo-1551650975-87deedd944c3?w=1200&auto=format&fit=crop&q=80" alt="Mobile App Development" class="hero-image">
        <h1>Mobile App Development</h1>
        <p class="lead">Building intuitive and engaging mobile applications for iOS and Android platforms.</p>
      </div>
      
      <div class="features-grid">
        <div class="feature-card">
          <img src="https://images.unsplash.com/photo-1512941937669-90a1b58e7e9c?w=600&auto=format&fit=crop&q=80" alt="Native Apps" class="feature-image">
          <h3>Native Apps</h3>
          <p>High-performance apps built specifically for iOS and Android.</p>
        </div>
        <div class="feature-card">
          <img src="https://images.unsplash.com/photo-1555774698-0b77e0d5fac6?w=600&auto=format&fit=crop&q=80" alt="Cross-Platform" class="feature-image">
          <h3>Cross-Platform</h3>
          <p>Efficient development for multiple platforms.</p>
        </div>
        <div class="feature-card">
          <img src="https://images.unsplash.com/photo-1596742578443-7682ef7b7057?w=600&auto=format&fit=crop&q=80" alt="User Experience" class="feature-image">
          <h3>Intuitive UX</h3>
          <p>Engaging and user-friendly interfaces.</p>
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
