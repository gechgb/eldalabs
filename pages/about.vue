<template>
  <div class="about-us">
    <!-- Hero Section -->
    <section class="hero-section about-hero">
      <div class="hero-overlay"></div>
      <div class="floating-shapes">
        <div class="shape shape-1"></div>
        <div class="shape shape-2"></div>
        <div class="shape shape-3"></div>
      </div>
      <div class="container">
        <div class="hero-content">
          <h1 class="hero-headline">About <span class="gradient-text">Elda Labs</span></h1>
          <p class="hero-subheadline">We are a team of innovators dedicated to building intelligent solutions for a smarter future.</p>
          <div class="hero-cta">
            <NuxtLink to="/contact" class="cta-button">Book Strategy Call</NuxtLink>
          </div>
        </div>
      </div>
    </section>

    <!-- Our Story Section -->
    <section class="section-padding story-section">
      <div class="container">
        <div class="glass-card story-card">
          <div class="section-header">
            <h2 class="section-title">Our <span class="gradient-text">Story</span></h2>
            <div class="title-underline"></div>
          </div>
          <div class="story-content">
            <div class="story-text">
              <p>Elda Labs was founded with a vision to transform how businesses leverage technology. We believe in creating solutions that are not just functional but revolutionary.</p>
              <p>Our journey began with a simple idea: to make advanced technology accessible to businesses of all sizes. Today, we're proud to be at the forefront of innovation, helping our clients navigate the digital landscape with confidence.</p>
            </div>
            <div class="story-image">
              <div class="image-container">
                <img src="https://images.unsplash.com/photo-1552664730-d307ca884978?ixlib=rb-4.0.3&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=1470&q=80" alt="Team collaboration" />
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- Our Team Section -->
    <section class="section-padding team-section">
      <div class="container">
        <div class="section-header">
          <h2 class="section-title">Meet Our <span class="gradient-text">Team</span></h2>
          <div class="title-underline"></div>
          <p class="section-subtitle">The brilliant minds behind our innovative solutions</p>
        </div>
        <div class="team-grid">
          <!-- Team Member Cards -->
          <div class="team-card glass-card">
            <div class="member-image">
              <img src="https://images.unsplash.com/photo-1560250097-0b93528c311a?ixlib=rb-4.0.3&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=687&q=80" alt="Team member" />
            </div>
            <div class="member-info">
              <h3 class="member-name">Alex Johnson</h3>
              <p class="member-role">CEO & Founder</p>
              <p class="member-bio">With over 15 years of experience in tech innovation, Alex leads our vision and strategy.</p>
              <div class="member-social">
                <a href="#" class="social-link" aria-label="LinkedIn">
                  <svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M16 8a6 6 0 0 1 6 6v7h-4v-7a2 2 0 0 0-2-2 2 2 0 0 0-2 2v7h-4v-7a6 6 0 0 1 6-6z"></path><rect x="2" y="9" width="4" height="12"></rect><circle cx="4" cy="4" r="2"></circle></svg>
                </a>
              </div>
            </div>
          </div>
          
          <div class="team-card glass-card">
            <div class="member-image">
              <img src="https://images.unsplash.com/photo-1573496359142-b8d87734a5a2?ixlib=rb-4.0.3&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=688&q=80" alt="Team member" />
            </div>
            <div class="member-info">
              <h3 class="member-name">Sarah Chen</h3>
              <p class="member-role">CTO</p>
              <p class="member-bio">Sarah's expertise in AI and machine learning drives our technical innovation.</p>
              <div class="member-social">
                <a href="#" class="social-link" aria-label="LinkedIn">
                  <svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M16 8a6 6 0 0 1 6 6v7h-4v-7a2 2 0 0 0-2-2 2 2 0 0 0-2 2v7h-4v-7a6 6 0 0 1 6-6z"></path><rect x="2" y="9" width="4" height="12"></rect><circle cx="4" cy="4" r="2"></circle></svg>
                </a>
              </div>
            </div>
          </div>
          
          <div class="team-card glass-card">
            <div class="member-image">
              <img src="https://images.unsplash.com/photo-1519085360753-af0119f7cbe7?ixlib=rb-4.0.3&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=687&q=80" alt="Team member" />
            </div>
            <div class="member-info">
              <h3 class="member-name">Michael Rodriguez</h3>
              <p class="member-role">Lead Developer</p>
              <p class="member-bio">Michael's coding expertise brings our most complex projects to life.</p>
              <div class="member-social">
                <a href="#" class="social-link" aria-label="LinkedIn">
                  <svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M16 8a6 6 0 0 1 6 6v7h-4v-7a2 2 0 0 0-2-2 2 2 0 0 0-2 2v7h-4v-7a6 6 0 0 1 6-6z"></path><rect x="2" y="9" width="4" height="12"></rect><circle cx="4" cy="4" r="2"></circle></svg>
                </a>
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- Our Values Section -->
    <section class="section-padding values-section">
      <div class="container">
        <div class="glass-card values-card">
          <div class="section-header">
            <h2 class="section-title">Our <span class="gradient-text">Values</span></h2>
            <div class="title-underline"></div>
          </div>
          <div class="values-grid">
            <div class="value-item">
              <div class="value-icon">
                <svg xmlns="http://www.w3.org/2000/svg" width="32" height="32" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><polygon points="12 2 15.09 8.26 22 9.27 17 14.14 18.18 21.02 12 17.77 5.82 21.02 7 14.14 2 9.27 8.91 8.26 12 2"></polygon></svg>
              </div>
              <h3>Innovation</h3>
              <p>We constantly push boundaries to create solutions that redefine what's possible.</p>
            </div>
            <div class="value-item">
              <div class="value-icon">
                <svg xmlns="http://www.w3.org/2000/svg" width="32" height="32" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M17 21v-2a4 4 0 0 0-4-4H5a4 4 0 0 0-4 4v2"></path><circle cx="9" cy="7" r="4"></circle><path d="M23 21v-2a4 4 0 0 0-3-3.87"></path><path d="M16 3.13a4 4 0 0 1 0 7.75"></path></svg>
              </div>
              <h3>Collaboration</h3>
              <p>We believe great ideas come from diverse perspectives working together.</p>
            </div>
            <div class="value-item">
              <div class="value-icon">
                <svg xmlns="http://www.w3.org/2000/svg" width="32" height="32" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M20.84 4.61a5.5 5.5 0 0 0-7.78 0L12 5.67l-1.06-1.06a5.5 5.5 0 0 0-7.78 7.78l1.06 1.06L12 21.23l7.78-7.78 1.06-1.06a5.5 5.5 0 0 0 0-7.78z"></path></svg>
              </div>
              <h3>Customer Focus</h3>
              <p>Our clients' success is our success. We're dedicated to exceeding expectations.</p>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- Contact Us Section -->
    <section class="section-padding contact-section">
      <div class="container">
        <div class="section-header">
          <h2 class="section-title">Ready to <span class="gradient-text">Work Together?</span></h2>
          <div class="title-underline"></div>
          <p class="section-subtitle">Let's discuss how we can help your business grow</p>
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
import { useHead } from '#imports';
import Footer from '~/components/Footer.vue';

useHead({
  title: 'Elda Labs | About Us'
})
</script>

<style scoped>
/* Hero Section Styles */
.about-hero {
  position: relative;
  padding: 12rem 0 8rem;
  overflow: hidden;
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

.hero-cta {
  margin-top: 2rem;
}

/* Section Styles */
.section-padding {
  padding: 6rem 0;
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

/* Glass Card Styles */
.glass-card {
  background: rgba(30, 30, 47, 0.7);
  backdrop-filter: blur(12px);
  -webkit-backdrop-filter: blur(12px);
  border-radius: var(--radius-lg);
  border: 1px solid rgba(255, 255, 255, 0.1);
  padding: 3rem;
  box-shadow: 0 8px 32px rgba(0, 0, 0, 0.1);
  transition: all 0.4s ease;
}

.glass-card:hover {
  transform: translateY(-5px);
  box-shadow: 0 12px 40px rgba(108, 99, 255, 0.2);
  border-color: rgba(108, 99, 255, 0.3);
}

/* Story Section Styles */
.story-content {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 3rem;
  align-items: center;
}

.story-text p {
  margin-bottom: 1.5rem;
  font-size: 1.1rem;
}

.image-container {
  border-radius: var(--radius-lg);
  overflow: hidden;
  box-shadow: 0 20px 40px rgba(0, 0, 0, 0.2);
  position: relative;
}

.image-container img {
  width: 100%;
  height: auto;
  display: block;
  transition: transform 0.5s ease;
}

.image-container:hover img {
  transform: scale(1.05);
}

/* Team Section Styles */
.team-grid {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
  gap: 2.5rem;
}

.team-card {
  overflow: hidden;
  transition: all 0.4s ease;
  padding: 0;
}

.member-image {
  height: 300px;
  overflow: hidden;
}

.member-image img {
  width: 100%;
  height: 100%;
  object-fit: cover;
  transition: transform 0.5s ease;
}

.team-card:hover .member-image img {
  transform: scale(1.1);
}

.member-info {
  padding: 1.5rem;
}

.member-name {
  font-size: 1.5rem;
  margin-bottom: 0.5rem;
}

.member-role {
  color: var(--accent-color);
  font-weight: 600;
  margin-bottom: 1rem;
}

.member-bio {
  margin-bottom: 1.5rem;
}

.member-social {
  display: flex;
  gap: 1rem;
}

.social-link {
  display: flex;
  align-items: center;
  justify-content: center;
  width: 36px;
  height: 36px;
  background: rgba(255, 255, 255, 0.1);
  border-radius: 50%;
  color: var(--neutral-900);
  transition: all 0.3s ease;
}

.social-link:hover {
  background: linear-gradient(135deg, var(--accent-color), var(--secondary-color));
  transform: translateY(-3px);
}

/* Values Section Styles */
.values-grid {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(280px, 1fr));
  gap: 2rem;
}

.value-item {
  text-align: center;
  padding: 2rem;
  transition: all 0.3s ease;
  border-radius: var(--radius-md);
}

.value-item:hover {
  background: rgba(255, 255, 255, 0.05);
  transform: translateY(-5px);
}

.value-icon {
  width: 70px;
  height: 70px;
  background: linear-gradient(135deg, rgba(108, 99, 255, 0.2), rgba(79, 172, 254, 0.2));
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
  margin: 0 auto 1.5rem;
  color: var(--accent-color);
}

.value-item h3 {
  margin-bottom: 1rem;
  font-size: 1.5rem;
}

/* Contact Section Styles */
.contact-section {
  text-align: center;
}

.contact-cta {
  margin-top: 3rem;
}

/* Responsive Styles */
@media (max-width: 992px) {
  .hero-headline {
    font-size: 3rem;
  }
  
  .story-content {
    grid-template-columns: 1fr;
  }
  
  .story-image {
    order: -1;
    margin-bottom: 2rem;
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
  
  .glass-card {
    padding: 2rem;
  }
}

@media (max-width: 480px) {
  .hero-headline {
    font-size: 2rem;
  }
  
  .section-title {
    font-size: 2rem;
  }
  
  .team-grid {
    grid-template-columns: 1fr;
  }
}
</style>
