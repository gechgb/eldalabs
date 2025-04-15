<template>
  <div class="contact">
    <!-- Hero Section -->
    <section class="hero" style="background-image: url('https://images.unsplash.com/photo-1550751827-4bd374c3f58b?ixlib=rb-4.0.3&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=1470&q=80');">
      <div class="container">
        <h1 class="hero-headline">Contact Us</h1>
        <p class="hero-subheadline">We'd love to hear from you!</p>
      </div>
    </section>

    <!-- Contact Form Section -->
    <section class="section-padding">
      <div class="container">
        <h2 class="section-title">Send us a Message</h2>
        <div class="contact-form">
          <form @submit.prevent="handleSubmit">
            <div class="form-group">
              <label for="name">Name</label>
              <input type="text" id="name" v-model="name" required>
            </div>
            <div class="form-group">
              <label for="email">Email</label>
              <input type="email" id="email" v-model="email" required>
            </div>
            <div class="form-group">
              <label for="message">Message</label>
              <textarea id="message" v-model="message" rows="5" required></textarea>
            </div>
            <button type="submit" class="cta-button">Send Message</button>
          </form>
        </div>
      </div>
    </section>

    <!-- Contact Information Section -->
    <section class="section-padding light-bg">
      <div class="container">
        <h2 class="section-title">Contact Information</h2>
        <div class="contact-info">
          <p><strong>Address:</strong> 123 Innovation Drive, Tech City, Addis Ababa, Ethiopia</p>
          <p><strong>Email:</strong> <a href="mailto:info@eldalabs.com">info@eldalabs.com</a></p>
          <p><strong>Phone:</strong> <a :href="`tel:+251912345678`">+251 912 345 678</a></p>
          <!-- Add Map Link/Embed if needed -->
        </div>
      </div>
    </section>
    <Footer />
  </div>
</template>

<script setup>
import { ref } from 'vue';
import { useHead } from '#imports';
import Footer from '~/components/Footer.vue';

const name = ref('');
const email = ref('');
const message = ref('');

const handleSubmit = () => {
  console.log('Form submitted:', { name: name.value, email: email.value, message: message.value });
  alert('Message sent successfully!');
  name.value = '';
  email.value = '';
  message.value = '';
};

useHead({
  title: 'Elda Labs | Contact Us',
  meta: [
    { name: 'description', content: 'Get in touch with Elda Labs. Contact us via email, phone, or fill out our contact form.' }
  ]
})
</script>

<style scoped>
/* Hero Section Styles */
.hero {
  background: linear-gradient(135deg, var(--primary-color), var(--accent-color));
  color: var(--neutral-900);
  padding: 10rem 0;
  text-align: center;
}

.hero-content {
  max-width: 800px;
  margin: 0 auto;
}

.hero-headline {
  font-size: 4rem;
  font-weight: 700;
  line-height: 1.2;
}

.hero-subheadline {
  font-size: 1.5rem;
  font-weight: 400;
  color: var(--neutral-500);
}

/* Section Styles */
.section-padding {
  padding: 6rem 0;
}

.section-title {
  margin-bottom: 4rem;
  font-size: 2.5rem;
  text-align: center;
}

.light-bg {
  background-color: var(--neutral-100);
}

/* Contact Form Styles */
.contact-form {
  background: var(--neutral-100);
  border-radius: 12px;
  padding: 2rem;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
}

.form-group {
  margin-bottom: 1.5rem;
}

.form-group label {
  display: block;
  color: var(--neutral-900);
  margin-bottom: 0.5rem;
}

.form-group input,
.form-group textarea {
  width: 100%;
  padding: 1rem;
  border: none;
  border-radius: 8px;
  background-color: var(--neutral-200);
  color: var(--neutral-800);
  font-size: 1rem;
}

/* Contact Information Styles */
.contact-info {
  background: var(--neutral-100);
  border-radius: 12px;
  padding: 2rem;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
}

.contact-info h2 {
  color: var(--neutral-900);
  margin-bottom: 1.5rem;
  font-size: 2rem;
}

.contact-info p {
  color: var(--neutral-500);
  margin-bottom: 1rem;
}

.contact-info a {
  color: var(--accent-color);
  text-decoration: none;
}

.contact-info a:hover {
  text-decoration: underline;
}
</style>
