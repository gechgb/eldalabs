<template>
  <section class="home">
    <div class="hero">
      <div class="hero-content container">
        <img src="https://images.unsplash.com/photo-1451187580459-43490279c0fa?w=1200&auto=format&fit=crop&q=80" alt="AI Technology" class="hero-image">
        <h1>AI & Software Solutions for Business Transformation</h1>
        <p>Elda Labs helps businesses innovate and grow with cutting-edge AI and software solutions. We partner with you to understand your unique challenges and deliver tailored technology to drive success.</p>
        <button class="primary-button">Learn More</button>
      </div>
    </div>

    <section class="services container">
      <h2>Our Services</h2>
      <div class="services-grid">
        <div class="service-card">
          <img src="https://images.unsplash.com/photo-1488229297570-58520851e868?w=600&auto=format&fit=crop&q=80" alt="AI Consulting" class="service-image">
          <h3>AI Consulting</h3>
          <p>Strategic AI guidance to transform your business processes and unlock new opportunities.</p>
          <a href="/services/ai-consulting">Learn more</a>
        </div>
        <div class="service-card">
          <img src="https://images.unsplash.com/photo-1461749280684-dccba630e2f6?w=600&auto=format&fit=crop&q=80" alt="Software Development" class="service-image">
          <h3>Software Development</h3>
          <p>Custom software solutions built with the latest technologies to meet your specific needs.</p>
          <a href="/services/software-development">Learn more</a>
        </div>
        <div class="service-card">
          <img src="https://images.unsplash.com/photo-1551288049-bebda4e38f71?w=600&auto=format&fit=crop&q=80" alt="Data Analytics" class="service-image">
          <h3>Data Analytics</h3>
          <p>Data-driven insights to optimize your operations and make informed business decisions.</p>
          <a href="/services/data-analytics">Learn more</a>
        </div>
        <div class="service-card">
          <img src="https://images.unsplash.com/photo-1544197150-b99a580bb7a8?w=600&auto=format&fit=crop&q=80" alt="Cloud Solutions" class="service-image">
          <h3>Cloud Solutions</h3>
          <p>Scalable and secure cloud infrastructure to power your applications and services.</p>
          <a href="/services/cloud-solutions">Learn more</a>
        </div>
      </div>
    </section>

    <section class="why-choose-us container">
      <h2>Why Choose Elda Labs?</h2>
      <div class="why-choose-grid">
        <div class="why-choose-card">
          <h3>Expertise</h3>
          <p>Deep expertise in AI, software development, and data analytics.</p>
        </div>
        <div class="why-choose-card">
          <h3>Custom Solutions</h3>
          <p>Tailored solutions to address your unique business challenges.</p>
        </div>
        <div class="why-choose-card">
          <h3>Innovation</h3>
          <p>Commitment to innovation and leveraging the latest technologies.</p>
        </div>
        <div class="why-choose-card">
          <h3>Partnership</h3>
          <p>Collaborative partnership approach to ensure your success.</p>
        </div>
      </div>
    </section>
  </section>
</template>

<script setup>
// You can add any necessary imports or logic here
</script>

<style scoped>
.home {
}

.hero {
  background-color: var(--primary-color);
  padding: 100px 0;
  text-align: center;
  color: var(--neutral-off-white);
  position: relative;
}

.hero-image {
  width: 100%;
  max-width: 800px;
  height: auto;
  margin-bottom: 2rem;
  border-radius: var(--radius-lg);
  box-shadow: var(--shadow-lg);
}

.service-image {
  width: 100%;
  height: 200px;
  object-fit: cover;
  border-radius: var(--radius-md);
  margin-bottom: 1.5rem;
}

.hero-content {
}

.hero-content h1 {
  font-size: 3rem;
  font-weight: 800;
  margin-bottom: 20px;
  text-shadow: 2px 2px 3px rgba(0, 0, 0, 0.3);
}

.hero-content p {
  font-size: 1.3rem;
  line-height: 1.7;
  margin-bottom: 30px;
  color: var(--neutral-off-white);
  text-shadow: 1px 1px 2px rgba(0, 0, 0, 0.3);
}

.primary-button {
  background-color: var(--accent-color); /* Electric Cyan / Aqua button */
  color: #fff;
  border: none;
  padding: 14px 35px;
  font-size: 1.2rem;
  cursor: pointer;
  border-radius: 7px;
  transition: background-color 0.3s ease, transform 0.3s ease;
}

.primary-button:hover {
  background-color: var(--accent-dark-color); /* Darker Electric Cyan on hover */
  transform: scale(1.05);
}

.services {
  padding: 80px 0;
  background-color: var(--accent-color); /* Electric Cyan / Aqua background for services */
}

.services h2, .why-choose-us h2 {
  text-align: center;
  font-size: 2.5rem;
  font-weight: 700;
  color: var(--neutral-off-white); /* Off-white text for headings */
  margin-bottom: 50px;
  text-shadow: 2px 2px 3px rgba(0, 0, 0, 0.3);
}

.services-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
  gap: 40px;
}

.service-card, .why-choose-card {
  background-color: var(--secondary-color);
  padding: 40px;
  border-radius: 7px;
  box-shadow: 0 7px 20px rgba(0, 0, 0, 0.08);
  text-align: center;
  transition: transform 0.3s ease, box-shadow 0.3s ease;
}

.service-card:hover, .why-choose-card:hover {
  transform: translateY(-5px);
  box-shadow: 0 10px 25px rgba(0, 0, 0, 0.1);
}

.service-card h3, .why-choose-card h3 {
  font-size: 1.7rem;
  color: var(--neutral-off-white); /* Off-white text for card headings */
  margin-bottom: 20px;
}

.service-card p, .why-choose-card p {
  color: var(--neutral-off-white); /* Off-white text for card content */
  line-height: 1.6;
  margin-bottom: 25px;
}

.service-card a {
  color: var(--accent-color); /* Electric Cyan / Aqua links */
  text-decoration: none;
  font-weight: 600;
  transition: color 0.3s ease;
}

.service-card a:hover {
  text-decoration: underline;
  color: var(--accent-dark-color); /* Darker Electric Cyan on hover */
}

.why-choose-us {
  padding-bottom: 80px;
  background-color: var(--primary-color); /* Deep Blue / Midnight for why choose us */
}

.why-choose-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
  gap: 30px;
}
</style>
