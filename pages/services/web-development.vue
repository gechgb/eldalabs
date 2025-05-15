<template>
  <div class="web-development-page">
    <section class="hero-section">
      <div class="container">
        <div class="hero-content">
          <h1 class="hero-headline">Web <span class="gradient-text">Development</span></h1>
          <p class="hero-subheadline">Crafting beautiful, high-performance websites and web applications that drive results.</p>
        </div>
      </div>
    </section>
      
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
</template>

<script setup>
// Add necessary script logic if needed later
</script>

<style scoped>
.web-development-page {
  background: var(--page-bg);
}

.hero-section {
  position: relative;
  min-height: 60vh;
  width: 100vw;
  overflow: hidden;
  background: var(--page-bg);
  margin: 0;
  padding: 2rem 0;
  display: flex;
  align-items: center;
  left: 50%;
  right: 50%;
  margin-left: -50vw;
  margin-right: -50vw;
  box-sizing: border-box; /* Added for predictable sizing */
}

.container {
  width: 100%;
  max-width: 100%;
  margin: 0;
  padding: 0 2rem;
  box-sizing: border-box; /* Added for predictable sizing */
}

.hero-content {
  position: relative;
  text-align: center;
  width: 100%;
}

.hero-headline {
  font-size: clamp(2.5rem, 5vw, 4rem);
  font-weight: 700;
  margin-bottom: 1.5rem;
  color: var(--text-primary);
  line-height: 1.2;
}

.hero-subheadline {
  font-size: clamp(1rem, 2vw, 1.25rem);
  color: var(--text-secondary);
  max-width: 800px;
  margin: 0 auto;
  line-height: 1.6;
}

.gradient-text {
  background: linear-gradient(135deg, var(--primary-color), var(--accent-color));
  -webkit-background-clip: text;
  background-clip: text;
  color: transparent;
  display: inline-block;
}

.features-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
  gap: 2rem;
  margin: 0 auto;
  padding: 3rem 2rem;
  max-width: 1200px;
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
