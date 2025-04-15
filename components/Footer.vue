<template>
  <footer class="footer section-padding">
    <div class="container footer-grid">

      <!-- Column 1: About & Contact -->
      <div class="footer-column">
        <h4 class="footer-heading">Elda Labs</h4>
        <p class="footer-about">
          Driving digital transformation with intelligent solutions and elegant design. We help businesses innovate and scale.
        </p>
        <div class="footer-contact">
          <p>123 Innovation Drive, Tech City</p>
          <p>Email: <a href="mailto:info@eldalabs.com">info@eldalabs.com</a></p>
          <p>Phone: <a href="tel:+1234567890">+1 (234) 567-890</a></p>
          <!-- Add Map Link/Embed if needed -->
        </div>
      </div>

      <!-- Column 2: Quick Links -->
      <div class="footer-column">
        <h4 class="footer-heading">Quick Links</h4>
        <ul class="footer-links">
          <li><NuxtLink to="/">Home</NuxtLink></li>
          <li><NuxtLink to="/about">About Us</NuxtLink></li>
          <li><NuxtLink to="/services">Services</NuxtLink></li>
          <li><NuxtLink to="/projects">Projects</NuxtLink></li>
          <li><NuxtLink to="/blog">Blog</NuxtLink></li>
          <li><NuxtLink to="/careers">Careers</NuxtLink></li>
          <li><NuxtLink to="/contact">Contact</NuxtLink></li>
        </ul>
      </div>

      <!-- Column 3: Newsletter -->
      <div class="footer-column">
        <h4 class="footer-heading">Stay Updated</h4>
        <p>Get the latest insights and news from Elda Labs.</p>
        <form class="newsletter-form" @submit.prevent="handleNewsletterSubmit">
          <div class="form-group">
            <input type="email" placeholder="Enter your email" required v-model="newsletterEmail" class="newsletter-input">
            <button type="submit" class="button button-primary newsletter-button">
              <span>Subscribe</span>
              <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><line x1="5" y1="12" x2="19" y2="12"></line><polyline points="12 5 19 12 12 19"></polyline></svg>
            </button>
          </div>
        </form>
      </div>

      <!-- Column 4: Social Links -->
      <div class="footer-column footer-social">
         <h4 class="footer-heading">Follow Us</h4>
         <div class="social-icons">
            <a href="#" target="_blank" aria-label="LinkedIn" class="social-icon">
              <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M16 8a6 6 0 0 1 6 6v7h-4v-7a2 2 0 0 0-2-2 2 2 0 0 0-2 2v7h-4v-7a6 6 0 0 1 6-6z"></path><rect x="2" y="9" width="4" height="12"></rect><circle cx="4" cy="4" r="2"></circle></svg>
            </a>
            <a href="#" target="_blank" aria-label="Instagram" class="social-icon">
              <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><rect x="2" y="2" width="20" height="20" rx="5" ry="5"></rect><path d="M16 11.37A4 4 0 1 1 12.63 8 4 4 0 0 1 16 11.37z"></path><line x1="17.5" y1="6.5" x2="17.51" y2="6.5"></line></svg>
            </a>
            <a href="#" target="_blank" aria-label="Twitter" class="social-icon">
              <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M22 4s-.7 2.1-2 3.4c1.6 10-9.4 17.3-18 11.6 2.2.1 4.4-.6 6-2C3 15.5.5 9.6 3 5c2.2 2.6 5.6 4.1 9 4-.9-4.2 4-6.6 7-3.8 1.1 0 3-1.2 3-1.2z"></path></svg>
            </a>
         </div>
      </div>

    </div>
    <div class="footer-bottom">
      <p>&copy; {{ new Date().getFullYear() }} Elda Labs. All rights reserved.</p>
    </div>
  </footer>
</template>

<script setup>
import { ref } from 'vue';

const newsletterEmail = ref('');

const handleNewsletterSubmit = () => {
  console.log('Newsletter submitted:', newsletterEmail.value);
  // Add actual form submission logic here (e.g., API call)
  newsletterEmail.value = ''; // Clear input after submission
  alert('Thank you for subscribing!'); // Placeholder feedback
};
</script>

<style scoped>
.footer {
  background: linear-gradient(135deg, var(--primary-color), var(--neutral-100));
  color: var(--neutral-800);
  padding-top: var(--space-xl, 48px);
  padding-bottom: var(--space-md, 24px);
  border-top: 1px solid rgba(255, 255, 255, 0.1);
  position: relative;
  overflow: hidden;
}

.footer::before {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background: url('https://images.unsplash.com/photo-1451187580459-43490279c0fa?w=1200&auto=format&fit=crop&q=80&auto=format&fit=crop&q=80') center/cover no-repeat;
  opacity: 0.05;
  z-index: 0;
}

.footer-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
  gap: var(--space-lg, 32px);
  margin-bottom: var(--space-lg, 32px);
  position: relative;
  z-index: 1;
}

.footer-column {
  backdrop-filter: blur(5px);
  -webkit-backdrop-filter: blur(5px);
  background: rgba(255, 255, 255, 0.03);
  border-radius: var(--radius-md);
  padding: 1.5rem;
  border: 1px solid rgba(255, 255, 255, 0.05);
  transition: transform 0.3s ease, box-shadow 0.3s ease;
}

.footer-column:hover {
  transform: translateY(-5px);
  box-shadow: 0 10px 30px rgba(0, 0, 0, 0.1);
}

.footer-heading {
  font-family: var(--font-heading, 'Poppins', sans-serif);
  font-size: 1.5rem;
  margin-bottom: 1.5rem;
  background: linear-gradient(135deg, var(--accent-color), var(--secondary-color));
  -webkit-background-clip: text;
  background-clip: text;
  color: transparent;
  display: inline-block;
  font-weight: 700;
}

.footer-about,
.footer-contact p {
  font-family: var(--font-body, 'Inter', sans-serif);
  font-size: 0.95rem;
  line-height: 1.6;
  color: var(--neutral-light-grey, #f8f9fa);
  margin-bottom: var(--space-xs, 8px);
}

.footer-contact a {
  color: var(--neutral-light-grey, #f8f9fa);
  text-decoration: none;
}

.footer-contact a:hover {
  color: var(--accent-color, #00E5FF);
  text-decoration: underline;
}

.footer-links {
  list-style: none;
  padding: 0;
  margin: 0;
}

.footer-links li {
  margin-bottom: var(--space-sm, 16px);
}

.footer-links li a {
  color: var(--neutral-light-grey, #f8f9fa);
  text-decoration: none;
  font-family: var(--font-body, 'Inter', sans-serif);
  transition: color 0.3s ease;
}

.footer-links li a:hover {
  color: var(--accent-color, #00E5FF);
}

.newsletter-form {
  margin-top: 1.5rem;
}

.form-group {
  display: flex;
  position: relative;
  box-shadow: 0 8px 20px rgba(0, 0, 0, 0.1);
  border-radius: var(--radius-md);
  overflow: hidden;
}

.newsletter-input {
  flex: 1;
  padding: 1rem 1.25rem;
  border: 1px solid rgba(255, 255, 255, 0.1);
  border-radius: var(--radius-md);
  background: rgba(255, 255, 255, 0.05);
  color: var(--neutral-800);
  width: 100%;
  font-size: 1rem;
  transition: all 0.3s ease;
}

.newsletter-input:focus {
  outline: none;
  background: rgba(255, 255, 255, 0.1);
  border-color: rgba(255, 255, 255, 0.2);
}

.newsletter-button {
  position: absolute;
  right: 5px;
  top: 5px;
  bottom: 5px;
  padding: 0 1.25rem;
  background: linear-gradient(135deg, var(--accent-color), var(--secondary-color));
  color: var(--neutral-900);
  border: none;
  border-radius: var(--radius-sm);
  cursor: pointer;
  transition: all 0.3s ease;
  display: flex;
  align-items: center;
  gap: 0.5rem;
}

.newsletter-button span {
  display: inline-block;
}

.newsletter-button svg {
  width: 18px;
  height: 18px;
  transition: transform 0.3s ease;
}

.newsletter-button:hover {
  background: linear-gradient(135deg, var(--secondary-color), var(--accent-color));
}

.newsletter-button:hover svg {
  transform: translateX(3px);
}

.footer-social {
  /* Specific alignment if needed */
}

.social-icons {
  display: flex;
  gap: 1.25rem;
  margin-top: 1.5rem;
}

.social-icon {
  display: inline-flex;
  align-items: center;
  justify-content: center;
  width: 45px;
  height: 45px;
  background: rgba(255, 255, 255, 0.05);
  color: var(--neutral-800);
  border-radius: 50%;
  text-decoration: none;
  transition: all 0.3s ease;
  border: 1px solid rgba(255, 255, 255, 0.1);
  position: relative;
  overflow: hidden;
  z-index: 1;
}

.social-icon::before {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background: linear-gradient(135deg, var(--accent-color), var(--secondary-color));
  z-index: -1;
  opacity: 0;
  transition: opacity 0.3s ease;
}

.social-icon:hover {
  color: var(--neutral-900);
  transform: translateY(-5px);
  box-shadow: 0 10px 20px rgba(0, 0, 0, 0.1);
}

.social-icon:hover::before {
  opacity: 1;
}

.social-icons a:hover {
  color: var(--accent-color, #00E5FF);
  transform: scale(1.1);
}

.footer-bottom {
  text-align: center;
  padding-top: var(--space-md, 24px);
  border-top: 1px solid rgba(255, 255, 255, 0.05);
  margin-top: var(--space-lg, 32px);
  font-size: 0.875rem;
  color: var(--neutral-500);
  position: relative;
  z-index: 1;
  backdrop-filter: blur(5px);
}

/* Responsive adjustments if needed */
@media (max-width: 768px) {
  .footer-grid {
    grid-template-columns: 1fr; /* Stack columns on smaller screens */
    text-align: center;
  }
  .social-icons {
    justify-content: center;
  }
  .newsletter-form {
    align-items: center;
  }
   .newsletter-form input[type="email"],
   .newsletter-form .button {
      max-width: 350px; /* Limit width on mobile */
   }
}
</style>
