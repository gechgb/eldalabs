<template>
  <div class="careers-page">
    <!-- Hero Section -->
    <section class="hero-section careers-hero">
      <div class="hero-background">
        <div class="gradient-blob blob-1"></div>
        <div class="gradient-blob blob-2"></div>
        <div class="gradient-blob blob-3"></div>
      </div>
      <div class="hero-overlay"></div>
      <div class="container">
        <div class="hero-content">
          <div class="hero-text">
            <h1 class="hero-headline">Join Our <span class="gradient-text">Team</span></h1>
            <p class="hero-subheadline">Be part of a team that's shaping the future of technology and innovation</p>
          </div>
        </div>
      </div>
    </section>

    <!-- Job Categories Section -->
    <section class="section-padding categories-section">
      <div class="container">
        <div class="section-header">
          <h2 class="section-title">Browse <span class="gradient-text">Opportunities</span></h2>
          <div class="title-underline"></div>
        </div>
        <div class="category-list">
          <button class="category-button active">All Positions</button>
          <button class="category-button">Engineering</button>
          <button class="category-button">Design</button>
          <button class="category-button">Product</button>
          <button class="category-button">Marketing</button>
          <button class="category-button">Operations</button>
        </div>
      </div>
    </section>

    <!-- Why Join Us Section -->
    <section class="section-padding why-join-section">
      <div class="container">
        <div class="section-header">
          <h2 class="section-title">Why Join <span class="gradient-text">Elda Labs</span></h2>
          <div class="title-underline"></div>
        </div>
        <div class="benefits-grid">
          <div class="benefit-card">
            <div class="benefit-icon">🚀</div>
            <h3>Innovation First</h3>
            <p>Work on cutting-edge technology and shape the future of AI</p>
          </div>
          <div class="benefit-card">
            <div class="benefit-icon">🌱</div>
            <h3>Growth & Learning</h3>
            <p>Continuous learning opportunities and career development</p>
          </div>
          <div class="benefit-card">
            <div class="benefit-icon">🤝</div>
            <h3>Inclusive Culture</h3>
            <p>Diverse, collaborative environment where every voice matters</p>
          </div>
          <div class="benefit-card">
            <div class="benefit-icon">💪</div>
            <h3>Work-Life Balance</h3>
            <p>Flexible schedules and remote work options</p>
          </div>
        </div>
      </div>
    </section>

    <!-- Open Positions Section -->
    <section class="section-padding positions-section">
      <div class="container">
        <div class="section-header">
          <h2 class="section-title">Open <span class="gradient-text">Positions</span></h2>
          <div class="title-underline"></div>
        </div>
        <div class="positions-grid">
          <div v-for="job in openPositions" :key="job.title" class="position-card">
            <div class="position-content">
              <span class="position-category">{{ job.category }}</span>
              <h3 class="position-title">{{ job.title }}</h3>
              <p class="position-location">{{ job.location }}</p>
              <p class="position-description">{{ job.description }}</p>
              <div class="position-tags">
                <span v-for="tag in job.tags" :key="tag" class="position-tag">{{ tag }}</span>
              </div>
            </div>
            <NuxtLink :to="job.link" class="apply-button">Apply Now</NuxtLink>
          </div>
        </div>
      </div>
    </section>

    <!-- Footer Section -->
    <Footer />
  </div>
</template>

<script setup>
import { useHead } from '#imports';
import Footer from '~/components/Footer.vue';

const openPositions = [
  {
    title: 'Senior AI Engineer',
    category: 'Engineering',
    location: 'Remote / San Francisco',
    description: 'Lead the development of our AI-powered solutions and mentor junior engineers.',
    tags: ['Machine Learning', 'Python', 'TensorFlow', 'Leadership'],
    link: '/careers/senior-ai-engineer'
  },
  {
    title: 'UX/UI Designer',
    category: 'Design',
    location: 'Remote / London',
    description: 'Create beautiful and intuitive user experiences for our digital products.',
    tags: ['Figma', 'User Research', 'Design Systems', 'Prototyping'],
    link: '/careers/ux-ui-designer'
  },
  {
    title: 'Product Manager',
    category: 'Product',
    location: 'Remote / New York',
    description: 'Drive product strategy and work closely with engineering and design teams.',
    tags: ['Strategy', 'Agile', 'Analytics', 'Leadership'],
    link: '/careers/product-manager'
  },
  {
    title: 'Full Stack Developer',
    category: 'Engineering',
    location: 'Remote / Berlin',
    description: 'Build and maintain scalable web applications using modern technologies.',
    tags: ['React', 'Node.js', 'TypeScript', 'AWS'],
    link: '/careers/full-stack-developer'
  }
];

useHead({
  title: 'Elda Labs | Careers'
});
</script>

<style scoped>
.careers-page {
  background: var(--page-bg);
}

/* Hero Section */
.hero-section {
  position: relative;
  height: 100vh;
  width: 100%;
  overflow: hidden;
  background: var(--page-bg);
  margin: 0;
  padding: 0;
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

.hero-section .container {
  position: relative;
  z-index: 3;
  text-align: center;
  width: 100%;
  height: 100vh;
  display: flex;
  align-items: center;
  justify-content: center;
  padding: 0 var(--spacing);
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

/* Categories Section */
.categories-section .container,
.why-join-section .container,
.positions-section .container {
  max-width: var(--max-width);
  margin: 0 auto;
  padding: 0 var(--spacing);
  width: 100%;
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

/* Benefits Grid */
.benefits-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
  gap: 2rem;
  margin: 3rem auto 0;
  max-width: var(--max-width);
  width: 100%;
}

.positions-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(320px, 1fr));
  gap: 2rem;
  margin: 3rem auto 0;
  max-width: var(--max-width);
  width: 100%;
}

.benefit-card {
  background: var(--card-bg);
  border-radius: var(--radius-lg);
  padding: 2rem;
  text-align: center;
  transition: transform 0.3s ease;
  border: 1px solid var(--border-color);
}

.benefit-card:hover {
  transform: translateY(-5px);
}

.benefit-icon {
  font-size: 2.5rem;
  margin-bottom: 1rem;
}

.benefit-card h3 {
  color: var(--text-primary);
  margin-bottom: 1rem;
}

.benefit-card p {
  color: var(--text-secondary);
  line-height: 1.6;
}

/* Positions Grid */
.positions-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
  gap: 2rem;
  margin-top: 3rem;
}

.position-card {
  background: var(--card-bg);
  border-radius: var(--radius-lg);
  padding: 2rem;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  transition: transform 0.3s ease;
  border: 1px solid var(--border-color);
}

.position-card:hover {
  transform: translateY(-5px);
}

.position-category {
  color: var(--primary-color);
  font-weight: 500;
  font-size: 0.875rem;
  margin-bottom: 0.5rem;
  display: block;
}

.position-title {
  color: var(--text-primary);
  font-size: 1.25rem;
  margin-bottom: 0.5rem;
}

.position-location {
  color: var(--text-secondary);
  font-size: 0.875rem;
  margin-bottom: 1rem;
}

.position-description {
  color: var(--text-secondary);
  margin-bottom: 1.5rem;
  line-height: 1.6;
}

.position-tags {
  display: flex;
  flex-wrap: wrap;
  gap: 0.5rem;
  margin-bottom: 1.5rem;
}

.position-tag {
  background: var(--primary-light);
  color: var(--primary-color);
  padding: 0.25rem 0.75rem;
  border-radius: var(--radius-full);
  font-size: 0.75rem;
}

.apply-button {
  background: var(--primary-color);
  color: var(--text-light);
  padding: 0.75rem 1.5rem;
  border-radius: var(--radius-full);
  text-align: center;
  text-decoration: none;
  font-weight: 500;
  transition: all 0.3s ease;
}

.apply-button:hover {
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
  .benefits-grid,
  .positions-grid {
    grid-template-columns: 1fr;
  }

  .category-list {
    flex-direction: column;
  }

  .category-button {
    width: 100%;
  }
}
</style>
