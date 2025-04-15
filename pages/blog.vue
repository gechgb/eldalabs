<template>
  <div class="blog-page">
    <!-- Hero Section -->
    <section class="hero-section blog-hero">
      <div class="hero-background">
        <div class="gradient-blob blob-1"></div>
        <div class="gradient-blob blob-2"></div>
        <div class="gradient-blob blob-3"></div>
      </div>
      <div class="hero-overlay"></div>
      <div class="container">
        <div class="hero-content">
          <div class="hero-text">
            <h1 class="hero-headline">Our <span class="gradient-text">Blog</span></h1>
            <p class="hero-subheadline">Insights, updates, and stories from the world of technology and innovation</p>
          </div>
        </div>
      </div>
    </section>

    <!-- Blog Categories Section -->
    <section class="section-padding categories-section">
      <div class="container">
        <div class="section-header">
          <h2 class="section-title">Explore <span class="gradient-text">Topics</span></h2>
          <div class="title-underline"></div>
        </div>
        <div class="category-list">
          <button class="category-button active">All</button>
          <button class="category-button">AI & ML</button>
          <button class="category-button">Tech Trends</button>
          <button class="category-button">Development</button>
          <button class="category-button">Business</button>
          <button class="category-button">Innovation</button>
        </div>
      </div>
    </section>

    <!-- Featured Posts Section -->
    <section class="section-padding featured-posts-section">
      <div class="container">
        <div class="featured-post-grid">
          <div v-for="post in featuredPosts" :key="post.title" class="blog-card featured">
            <div class="blog-card-image" :style="{ backgroundImage: `url(${post.image})` }">
              <div class="blog-card-overlay"></div>
              <span class="featured-tag">Featured</span>
            </div>
            <div class="blog-card-content">
              <div class="blog-meta">
                <span class="blog-category">{{ post.category }}</span>
                <span class="blog-date">{{ post.date }}</span>
              </div>
              <h3 class="blog-title">{{ post.title }}</h3>
              <p class="blog-excerpt">{{ post.excerpt }}</p>
              <NuxtLink :to="post.link" class="read-more">Read More</NuxtLink>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- Latest Posts Grid -->
    <section class="section-padding latest-posts-section">
      <div class="container">
        <div class="section-header">
          <h2 class="section-title">Latest <span class="gradient-text">Articles</span></h2>
          <div class="title-underline"></div>
        </div>
        <div class="blog-grid">
          <div v-for="post in latestPosts" :key="post.title" class="blog-card">
            <div class="blog-card-image" :style="{ backgroundImage: `url(${post.image})` }">
              <div class="blog-card-overlay"></div>
            </div>
            <div class="blog-card-content">
              <div class="blog-meta">
                <span class="blog-category">{{ post.category }}</span>
                <span class="blog-date">{{ post.date }}</span>
              </div>
              <h3 class="blog-title">{{ post.title }}</h3>
              <p class="blog-excerpt">{{ post.excerpt }}</p>
              <NuxtLink :to="post.link" class="read-more">Read More</NuxtLink>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- Newsletter Section -->
    <section class="section-padding newsletter-section">
      <div class="container">
        <div class="newsletter-content">
          <h2 class="newsletter-title">Stay <span class="gradient-text">Updated</span></h2>
          <p class="newsletter-description">Subscribe to our newsletter for the latest insights and updates</p>
          <form class="newsletter-form">
            <input type="email" placeholder="Enter your email" class="newsletter-input">
            <button type="submit" class="newsletter-button">Subscribe</button>
          </form>
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

const featuredPosts = [
  {
    title: 'The Future of AI in Enterprise Solutions',
    excerpt: 'Exploring how artificial intelligence is reshaping business operations and decision-making processes.',
    image: 'https://images.unsplash.com/photo-1620712943543-bcc4688e7485?w=1470&q=80',
    category: 'AI & ML',
    date: 'May 15, 2024',
    link: '/blog/ai-enterprise-solutions'
  },
  {
    title: 'Building Scalable Web Applications',
    excerpt: 'Best practices and architectural patterns for creating robust, scalable web applications.',
    image: 'https://images.unsplash.com/photo-1460925895917-afdab827c52f?w=1470&q=80',
    category: 'Development',
    date: 'May 12, 2024',
    link: '/blog/scalable-web-apps'
  }
];

const latestPosts = [
  {
    title: 'Emerging Tech Trends in 2024',
    excerpt: 'A comprehensive look at the technology trends shaping the future of digital innovation.',
    image: 'https://images.unsplash.com/photo-1519389950473-47ba0277781c?w=1470&q=80',
    category: 'Tech Trends',
    date: 'May 10, 2024',
    link: '/blog/tech-trends-2024'
  },
  {
    title: 'The Rise of Edge Computing',
    excerpt: 'Understanding the impact of edge computing on modern application architecture.',
    image: 'https://images.unsplash.com/photo-1551288049-bebda4e38f71?w=1470&q=80',
    category: 'Innovation',
    date: 'May 8, 2024',
    link: '/blog/edge-computing'
  },
  {
    title: 'Digital Transformation Success Stories',
    excerpt: 'Real-world examples of successful digital transformation initiatives.',
    image: 'https://images.unsplash.com/photo-1552664730-d307ca884978?w=1470&q=80',
    category: 'Business',
    date: 'May 5, 2024',
    link: '/blog/transformation-success'
  },
  {
    title: 'Cybersecurity Best Practices',
    excerpt: 'Essential security measures for protecting modern digital enterprises.',
    image: 'https://images.unsplash.com/photo-1563986768609-322da13575f3?w=1470&q=80',
    category: 'Tech Trends',
    date: 'May 3, 2024',
    link: '/blog/cybersecurity-practices'
  }
];

useHead({
  title: 'Elda Labs | Blog'
});
</script>

<style scoped>
.blog-page {
  background: var(--page-bg);
}

/* Hero Section */
.hero-section {
  position: relative;
  padding: 8rem 0;
  overflow: hidden;
  background: linear-gradient(135deg, var(--primary-dark), var(--primary-color));
}

.hero-headline {
  font-size: clamp(2.5rem, 5vw, 4.5rem);
  font-weight: 700;
  line-height: 1.1;
  margin-bottom: 1.5rem;
  color: var(--text-light);
}

.hero-subheadline {
  font-size: clamp(1.25rem, 2vw, 1.75rem);
  font-weight: 400;
  color: var(--neutral-500);
  max-width: 600px;
  margin: 0 auto;
  line-height: 1.6;
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

/* Blog Cards */
.featured-post-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
  gap: 2rem;
  margin-bottom: 4rem;
}

.blog-grid {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
  gap: 2rem;
}

.blog-card {
  background: var(--card-bg);
  border-radius: var(--radius-lg);
  overflow: hidden;
  transition: transform 0.3s ease;
  border: 1px solid var(--border-color);
}

.blog-card:hover {
  transform: translateY(-5px);
}

.blog-card-image {
  height: 200px;
  background-size: cover;
  background-position: center;
  position: relative;
}

.blog-card-overlay {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background: linear-gradient(to bottom, rgba(0,0,0,0) 0%, rgba(0,0,0,0.7) 100%);
}

.featured-tag {
  position: absolute;
  top: 1rem;
  right: 1rem;
  background: var(--accent-color);
  color: var(--text-light);
  padding: 0.5rem 1rem;
  border-radius: var(--radius-full);
  font-size: 0.875rem;
}

.blog-card-content {
  padding: 1.5rem;
}

.blog-meta {
  display: flex;
  gap: 1rem;
  margin-bottom: 1rem;
  font-size: 0.875rem;
}

.blog-category {
  color: var(--primary-color);
  font-weight: 500;
}

.blog-date {
  color: var(--text-muted);
}

.blog-title {
  font-size: 1.25rem;
  margin-bottom: 1rem;
  color: var(--text-primary);
  line-height: 1.4;
}

.blog-excerpt {
  color: var(--text-secondary);
  margin-bottom: 1.5rem;
  line-height: 1.6;
}

.read-more {
  color: var(--primary-color);
  text-decoration: none;
  font-weight: 500;
  display: inline-flex;
  align-items: center;
  gap: 0.5rem;
}

.read-more:hover {
  text-decoration: underline;
}

/* Newsletter Section */
.newsletter-section {
  background: linear-gradient(135deg, var(--primary-dark), var(--primary-color));
  color: var(--text-light);
  text-align: center;
  border-radius: var(--radius-lg);
  margin: 4rem 0;
}

.newsletter-content {
  max-width: 600px;
  margin: 0 auto;
}

.newsletter-title {
  font-size: 2.5rem;
  margin-bottom: 1rem;
}

.newsletter-description {
  color: var(--text-light-muted);
  margin-bottom: 2rem;
}

.newsletter-form {
  display: flex;
  gap: 1rem;
  max-width: 500px;
  margin: 0 auto;
}

.newsletter-input {
  flex: 1;
  padding: 1rem;
  border: none;
  border-radius: var(--radius-full);
  background: rgba(255,255,255,0.1);
  color: var(--text-light);
  outline: none;
}

.newsletter-input::placeholder {
  color: var(--text-light-muted);
}

.newsletter-button {
  padding: 1rem 2rem;
  border: none;
  border-radius: var(--radius-full);
  background: var(--accent-color);
  color: var(--text-light);
  font-weight: 500;
  cursor: pointer;
  transition: all 0.3s ease;
}

.newsletter-button:hover {
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
  .newsletter-form {
    flex-direction: column;
  }

  .newsletter-button {
    width: 100%;
  }
}
</style>
