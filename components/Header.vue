<template>
  <header class="header" :class="{ 'scrolled': isScrolled }">
    <div class="container">
      <nav class="nav">
        <NuxtLink to="/" class="logo">
          <span class="logo-text">ELDA</span>
          <span class="logo-accent">LABS</span>
        </NuxtLink>

        <!-- Hamburger Button -->
        <button class="hamburger" @click="toggleMobileMenu" :class="{ 'is-active': isMobileMenuOpen }" aria-label="Menu">
          <span></span>
          <span></span>
          <span></span>
        </button>

        <!-- Desktop Menu -->
        <ul class="menu desktop-menu">
          <li><NuxtLink to="/" class="nav-link">Home</NuxtLink></li>
          <li><NuxtLink to="/about" class="nav-link">About Us</NuxtLink></li>
          <li><NuxtLink to="/services" class="nav-link">Services</NuxtLink></li>
          <li><NuxtLink to="/projects" class="nav-link">Projects</NuxtLink></li>
          <li><NuxtLink to="/blog" class="nav-link">Blog</NuxtLink></li>
          <li><NuxtLink to="/careers" class="nav-link">Careers</NuxtLink></li>
          <li><NuxtLink to="/aibot-test" class="nav-link">Test Bots</NuxtLink></li>
          <li><NuxtLink to="/contact" class="cta-button">Book Strategy Call</NuxtLink></li>
        </ul>
      </nav>
    </div>

    <!-- Mobile Menu -->
    <div class="mobile-menu-container" :class="{ 'is-open': isMobileMenuOpen }">
      <div class="mobile-menu-header">
        <NuxtLink to="/" class="logo" @click="closeMobileMenu">
          <span class="logo-text">ELDA</span>
          <span class="logo-accent">LABS</span>
        </NuxtLink>
        <button class="close-menu" @click="closeMobileMenu" aria-label="Close menu">
          <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><line x1="18" y1="6" x2="6" y2="18"></line><line x1="6" y1="6" x2="18" y2="18"></line></svg>
        </button>
      </div>
      <ul class="menu mobile-menu">
        <li><NuxtLink to="/" @click="closeMobileMenu" class="nav-link">Home</NuxtLink></li>
        <li><NuxtLink to="/about" @click="closeMobileMenu" class="nav-link">About Us</NuxtLink></li>
        <li><NuxtLink to="/services" @click="closeMobileMenu" class="nav-link">Services</NuxtLink></li>
        <li><NuxtLink to="/projects" @click="closeMobileMenu" class="nav-link">Projects</NuxtLink></li>
        <li><NuxtLink to="/blog" @click="closeMobileMenu" class="nav-link">Blog</NuxtLink></li>
        <li><NuxtLink to="/careers" @click="closeMobileMenu" class="nav-link">Careers</NuxtLink></li>
        <li><NuxtLink to="/test-bots" @click="closeMobileMenu" class="nav-link">Test Bots</NuxtLink></li>
        <li><NuxtLink to="/contact" @click="closeMobileMenu" class="nav-link cta-mobile">Contact Us</NuxtLink></li>
      </ul>
      <div class="mobile-menu-footer">
        <div class="social-icons">
          <a href="#" target="_blank" aria-label="LinkedIn" class="social-icon">
            <svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M16 8a6 6 0 0 1 6 6v7h-4v-7a2 2 0 0 0-2-2 2 2 0 0 0-2 2v7h-4v-7a6 6 0 0 1 6-6z"></path><rect x="2" y="9" width="4" height="12"></rect><circle cx="4" cy="4" r="2"></circle></svg>
          </a>
          <a href="#" target="_blank" aria-label="Twitter" class="social-icon">
            <svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M22 4s-.7 2.1-2 3.4c1.6 10-9.4 17.3-18 11.6 2.2.1 4.4-.6 6-2C3 15.5.5 9.6 3 5c2.2 2.6 5.6 4.1 9 4-.9-4.2 4-6.6 7-3.8 1.1 0 3-1.2 3-1.2z"></path></svg>
          </a>
          <a href="#" target="_blank" aria-label="Instagram" class="social-icon">
            <svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><rect x="2" y="2" width="20" height="20" rx="5" ry="5"></rect><path d="M16 11.37A4 4 0 1 1 12.63 8 4 4 0 0 1 16 11.37z"></path><line x1="17.5" y1="6.5" x2="17.51" y2="6.5"></line></svg>
          </a>
        </div>
      </div>
    </div>
  </header>
</template>

<script setup>
import { ref, onMounted, onUnmounted } from 'vue';

const isMobileMenuOpen = ref(false);
const isScrolled = ref(false);

const toggleMobileMenu = () => {
  isMobileMenuOpen.value = !isMobileMenuOpen.value;
};

const closeMobileMenu = () => {
  isMobileMenuOpen.value = false;
};

const handleScroll = () => {
  isScrolled.value = window.scrollY > 50;
};

onMounted(() => {
  window.addEventListener('scroll', handleScroll);
});

onUnmounted(() => {
  window.removeEventListener('scroll', handleScroll);
});
</script>

<style scoped>
.header {
  background-color: rgba(26, 27, 75, 0.2);
  padding: 1.25rem 0;
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  z-index: 1000;
  width: 100%;
  box-shadow: 0 8px 32px rgba(0, 0, 0, 0.05);
  backdrop-filter: blur(12px);
  -webkit-backdrop-filter: blur(12px);
  border-bottom: 1px solid rgba(255, 255, 255, 0.05);
  transition: all 0.4s cubic-bezier(0.16, 1, 0.3, 1);
}

.header.scrolled {
  background-color: rgba(26, 27, 75, 0.85);
  padding: 0.85rem 0;
  box-shadow: 0 10px 30px rgba(0, 0, 0, 0.15);
}

.container {
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 20px;
  display: flex;
  justify-content: space-between;
  align-items: center;
  width: 100%;
}

.nav {
  display: flex;
  justify-content: flex-start;
  align-items: center;
  width: 100%;
  gap: 3rem;
}

.logo {
  font-size: 1.75rem;
  font-weight: 700;
  color: var(--neutral-900);
  text-decoration: none;
  transition: all 0.3s ease;
  letter-spacing: 1px;
  text-transform: uppercase;
  display: flex;
  align-items: center;
}

.logo-text {
  background: linear-gradient(135deg, var(--neutral-900), var(--neutral-800));
  -webkit-background-clip: text;
  background-clip: text;
  color: transparent;
}

.logo-accent {
  background: linear-gradient(135deg, var(--accent-color), var(--secondary-color));
  -webkit-background-clip: text;
  background-clip: text;
  color: transparent;
  margin-left: 5px;
}

.logo:hover {
  transform: translateY(-2px);
}

/* Base Menu Styles */
.menu {
  list-style: none;
  padding: 0;
  margin: 0;
}

.nav-link {
  color: var(--neutral-900);
  text-decoration: none;
  font-weight: 500;
  transition: all 0.3s cubic-bezier(0.25, 1, 0.5, 1);
  padding: 0.5rem 0.75rem;
  border-radius: var(--radius-sm);
  position: relative;
  font-size: 0.95rem;
  letter-spacing: 0.5px;
}

.nav-link:hover {
  color: var(--accent-color);
}

.nav-link::after {
  content: '';
  position: absolute;
  width: 0;
  height: 2px;
  bottom: -2px;
  left: 0;
  background: linear-gradient(90deg, var(--accent-color), var(--secondary-color));
  transition: width 0.3s cubic-bezier(0.25, 1, 0.5, 1);
  opacity: 0;
  transform-origin: left;
}

.nav-link:hover::after {
  width: 100%;
  opacity: 1;
}

/* Desktop Menu Styles */
.desktop-menu {
  display: flex;
  align-items: center;
  gap: 0.75rem;
  margin-left: auto;
}

.desktop-menu li {
  position: relative;
}

.desktop-menu .nav-link {
  padding: 0.5rem 0.75rem;
  font-weight: 600;
  white-space: nowrap;
  letter-spacing: 0.02em;
}

/* CTA Button Styles */
.cta-button {
  background: linear-gradient(135deg, var(--accent-color), var(--secondary-color));
  color: var(--neutral-900);
  padding: 0.625rem 1.25rem;
  border-radius: var(--radius-md);
  font-weight: 600;
  text-decoration: none;
  transition: all 0.3s cubic-bezier(0.25, 1, 0.5, 1);
  box-shadow: 0 4px 15px rgba(108, 99, 255, 0.3);
  position: relative;
  overflow: hidden;
  z-index: 1;
  border: 1px solid rgba(255, 255, 255, 0.1);
}

.cta-button::before {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background: linear-gradient(135deg, var(--secondary-color), var(--accent-color));
  z-index: -1;
  transition: opacity 0.3s cubic-bezier(0.25, 1, 0.5, 1);
  opacity: 0;
}

.cta-button:hover {
  transform: translateY(-3px);
  box-shadow: 0 8px 25px rgba(108, 99, 255, 0.5);
}

.cta-button:hover::before {
  opacity: 1;
}

/* Hamburger Button Styles */
.hamburger {
  display: none;
  background: none;
  border: none;
  cursor: pointer;
  padding: 10px;
  z-index: 1010;
  transition: all 0.3s ease;
}

.hamburger:hover {
  transform: scale(1.05);
}

.hamburger span {
  display: block;
  width: 28px;
  height: 2px;
  background: linear-gradient(90deg, var(--accent-color), var(--secondary-color));
  margin: 6px 0;
  transition: all 0.4s cubic-bezier(0.68, -0.6, 0.32, 1.6);
  border-radius: 2px;
}

/* Hamburger Active State (Cross) */
.hamburger.is-active span:nth-child(1) {
  transform: rotate(45deg) translate(5px, 5px);
}

.hamburger.is-active span:nth-child(2) {
  opacity: 0;
  transform: translateX(-20px);
}

.hamburger.is-active span:nth-child(3) {
  transform: rotate(-45deg) translate(7px, -6px);
}

/* Mobile Menu Container Styles */
.mobile-menu-container {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100vh;
  background: linear-gradient(135deg, rgba(26, 27, 75, 0.98), rgba(108, 99, 255, 0.95));
  backdrop-filter: blur(15px);
  -webkit-backdrop-filter: blur(15px);
  z-index: 999;
  transform: translateX(100%);
  transition: all 0.5s cubic-bezier(0.16, 1, 0.3, 1);
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  padding: 2rem;
  overflow-y: auto;
}

.mobile-menu-container.is-open {
  transform: translateX(0);
  box-shadow: -10px 0 30px rgba(0, 0, 0, 0.2);
}

.mobile-menu-header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  width: 100%;
  margin-bottom: 2rem;
}

.close-menu {
  background: rgba(255, 255, 255, 0.1);
  border: none;
  width: 40px;
  height: 40px;
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
  cursor: pointer;
  color: var(--neutral-900);
  transition: all 0.3s ease;
  border: 1px solid rgba(255, 255, 255, 0.05);
}

.close-menu:hover {
  background: rgba(255, 255, 255, 0.2);
  transform: rotate(90deg);
}

/* Mobile Menu Styles */
.mobile-menu {
  display: flex;
  flex-direction: column;
  align-items: center;
  width: 100%;
  gap: 1.25rem;
  padding: 2rem 0;
}

.mobile-menu li {
  width: 100%;
  text-align: center;
}

.mobile-menu li a {
  font-size: 1.5rem;
  font-weight: 600;
  color: var(--neutral-900);
  display: block;
  padding: 12px;
  border-radius: var(--radius-md);
  transition: all 0.3s ease;
}

.mobile-menu li a:hover {
  background: rgba(255, 255, 255, 0.1);
  transform: translateX(5px);
}

.cta-mobile {
  margin-top: 1rem;
  background: rgba(255, 255, 255, 0.15);
  border: 1px solid rgba(255, 255, 255, 0.1);
  box-shadow: 0 4px 15px rgba(0, 0, 0, 0.1);
}

.mobile-menu-footer {
  margin-top: 2rem;
  width: 100%;
  display: flex;
  justify-content: center;
}

.social-icons {
  display: flex;
  gap: 1rem;
}

.social-icon {
  display: flex;
  align-items: center;
  justify-content: center;
  width: 40px;
  height: 40px;
  background: rgba(255, 255, 255, 0.1);
  border-radius: 50%;
  color: var(--neutral-900);
  transition: all 0.3s ease;
  border: 1px solid rgba(255, 255, 255, 0.05);
}

.social-icon:hover {
  background: linear-gradient(135deg, var(--accent-color), var(--secondary-color));
  transform: translateY(-3px);
}

/* Responsive Breakpoint */
@media (max-width: 992px) {
  .desktop-menu {
    display: none;
  }
  .hamburger {
    display: block;
  }
  .nav {
    justify-content: space-between;
  }
}

@media (max-width: 480px) {
  .mobile-menu li a {
    font-size: 1.25rem;
  }
  
  .mobile-menu-container {
    padding: 1.5rem;
  }
}
</style>
