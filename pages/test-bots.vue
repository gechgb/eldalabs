<template>
  <div class="test-bots-page">
    <!-- Hero Section -->
    <section class="hero-section test-bots-hero">
      <div class="hero-background">
        <div class="gradient-blob blob-1"></div>
        <div class="gradient-blob blob-2"></div>
        <div class="gradient-blob blob-3"></div>
      </div>
      <div class="hero-overlay"></div>
      <div class="container">
        <div class="hero-content">
          <h1 class="hero-headline">Industry-Specific <span class="gradient-text">AI Bots</span></h1>
          <p class="hero-subheadline">Experience tailored AI solutions for your industry</p>
          <div class="hero-cta">
            <NuxtLink to="/contact" class="cta-button">Try Now</NuxtLink>
          </div>
        </div>
      </div>
    </section>

    <!-- Industry Selection Section -->
    <section class="section-padding industry-section">
      <div class="container">
        <h2 class="section-title">Select Your Industry</h2>
        <div class="industry-grid">
          <div v-for="industry in industries" :key="industry.id" 
               class="industry-card" 
               :class="{ 'active': selectedIndustry === industry.id }"
               @click="selectIndustry(industry.id)">
            <div class="industry-icon">{{ industry.icon }}</div>
            <h3>{{ industry.name }}</h3>
            <p>{{ industry.description }}</p>
          </div>
        </div>
      </div>
    </section>

    <!-- Chat Interface Section -->
    <section class="section-padding chat-section" v-if="selectedIndustry">
      <div class="container">
        <div class="chat-container glass-card">
          <div class="chat-header">
            <div class="bot-info">
              <div class="bot-avatar">{{ selectedIndustryData.icon }}</div>
              <div class="bot-status">
                <h3>{{ selectedIndustryData.botName }}</h3>
                <span class="status-indicator">Online</span>
              </div>
            </div>
          </div>
          
          <div class="chat-messages" ref="messageContainer">
            <div v-for="(message, index) in messages" :key="index" 
                 :class="['message', message.type]">
              <div class="message-content">
                <p>{{ message.text }}</p>
                <span class="message-time">{{ message.time }}</span>
              </div>
            </div>
          </div>

          <div class="chat-input">
            <input 
              v-model="newMessage" 
              @keyup.enter="sendMessage"
              type="text" 
              placeholder="Type your message here..."
              class="message-input"
            />
            <button @click="sendMessage" class="send-button">
              <span>Send</span>
            </button>
          </div>
        </div>

        <div class="features-grid">
          <div class="feature-card">
            <div class="feature-icon">🎯</div>
            <h3>Smart Responses</h3>
            <p>Advanced AI algorithms provide contextually relevant answers</p>
          </div>
          <div class="feature-card">
            <div class="feature-icon">⚡</div>
            <h3>Real-time Processing</h3>
            <p>Lightning-fast response times for seamless conversations</p>
          </div>
          <div class="feature-card">
            <div class="feature-icon">🔄</div>
            <h3>Continuous Learning</h3>
            <p>Our AI improves with every interaction</p>
          </div>
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

const industries = ref([
  {
    id: 'ecommerce',
    name: 'E-commerce',
    icon: '🛍️',
    description: 'AI solutions for online retail and customer service',
    botName: 'RetailBot'
  },
  {
    id: 'healthcare',
    name: 'Healthcare',
    icon: '⚕️',
    description: 'Smart assistance for healthcare providers and patients',
    botName: 'HealthBot'
  },
  {
    id: 'finance',
    name: 'Finance',
    icon: '💰',
    description: 'AI-powered financial advisory and services',
    botName: 'FinanceBot'
  },
  {
    id: 'education',
    name: 'Education',
    icon: '📚',
    description: 'Intelligent learning and teaching assistance',
    botName: 'EduBot'
  }
]);

const selectedIndustry = ref(null);
const messages = ref([]);
const newMessage = ref('');
const messageContainer = ref(null);

const selectedIndustryData = computed(() => {
  return industries.value.find(industry => industry.id === selectedIndustry.value) || {};
});

const selectIndustry = (industryId) => {
  selectedIndustry.value = industryId;
  messages.value = [{
    type: 'bot',
    text: `Hello! I'm ${selectedIndustryData.value.botName}. How can I assist you with your ${selectedIndustryData.value.name.toLowerCase()} needs?`,
    time: new Date().toLocaleTimeString('en-US', { hour: 'numeric', minute: 'numeric', hour12: true })
  }];
  scrollToBottom();
};

const sendMessage = () => {
  if (newMessage.value.trim() === '') return;

  const currentTime = new Date().toLocaleTimeString('en-US', {
    hour: 'numeric',
    minute: 'numeric',
    hour12: true
  });

  messages.value.push({
    type: 'user',
    text: newMessage.value,
    time: currentTime
  });

  // Simulate bot response
  setTimeout(() => {
    messages.value.push({
      type: 'bot',
      text: 'I understand your message. How else can I assist you?',
      time: currentTime
    });
    scrollToBottom();
  }, 1000);

  newMessage.value = '';
  scrollToBottom();
};

const scrollToBottom = () => {
  setTimeout(() => {
    if (messageContainer.value) {
      messageContainer.value.scrollTop = messageContainer.value.scrollHeight;
    }
  }, 100);
};

useHead({
  title: 'Elda Labs | Test Our AI Bots'
});
</script>

<style scoped>
.test-bots-page {
  background: var(--page-bg);
}

.industry-section {
  padding: 4rem 0;
}

.section-title {
  text-align: center;
  font-size: 2.5rem;
  margin-bottom: 3rem;
  background: linear-gradient(135deg, var(--accent-color), var(--secondary-color));
  -webkit-background-clip: text;
  background-clip: text;
  color: transparent;
}

.industry-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
  gap: 2rem;
  margin-top: 2rem;
}

.industry-card {
  background: rgba(255, 255, 255, 0.05);
  border-radius: var(--radius-lg);
  padding: 2rem;
  text-align: center;
  transition: all 0.3s ease;
  cursor: pointer;
  border: 1px solid rgba(255, 255, 255, 0.1);
}

.industry-card:hover {
  transform: translateY(-5px);
  background: rgba(255, 255, 255, 0.1);
  box-shadow: 0 10px 30px rgba(0, 0, 0, 0.1);
}

.industry-card.active {
  background: linear-gradient(135deg, var(--accent-color), var(--secondary-color));
  border: none;
}

.industry-icon {
  font-size: 3rem;
  margin-bottom: 1rem;
}

.industry-card h3 {
  font-size: 1.5rem;
  margin-bottom: 1rem;
  color: var(--neutral-900);
}

.industry-card p {
  color: var(--neutral-700);
  font-size: 0.9rem;
  line-height: 1.5;
}

.industry-card.active h3,
.industry-card.active p {
  color: var(--neutral-900);
}

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

.chat-container {
  max-width: 800px;
  margin: 0 auto;
  height: 600px;
  display: flex;
  flex-direction: column;
  background: var(--card-bg);
  border: 1px solid var(--border-color);
  border-radius: var(--radius-lg);
  overflow: hidden;
}

.chat-header {
  padding: 1rem;
  border-bottom: 1px solid var(--border-color);
  background: rgba(255, 255, 255, 0.05);
}

.bot-info {
  display: flex;
  align-items: center;
  gap: 1rem;
}

.bot-avatar {
  width: 40px;
  height: 40px;
  background: var(--primary-light);
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 1.5rem;
}

.bot-status h3 {
  margin: 0;
  color: var(--text-primary);
}

.status-indicator {
  color: var(--success-color);
  font-size: 0.875rem;
}

.chat-messages {
  flex: 1;
  padding: 1rem;
  overflow-y: auto;
  display: flex;
  flex-direction: column;
  gap: 1rem;
}

.message {
  max-width: 80%;
  padding: 0.75rem 1rem;
  border-radius: var(--radius-lg);
  animation: fadeIn 0.3s ease;
}

.message.bot {
  align-self: flex-start;
  background: var(--primary-light);
  color: var(--text-primary);
}

.message.user {
  align-self: flex-end;
  background: var(--primary-color);
  color: var(--text-light);
}

.message-content {
  position: relative;
}

.message-time {
  font-size: 0.75rem;
  opacity: 0.7;
  margin-top: 0.25rem;
  display: block;
}

.chat-input {
  padding: 1rem;
  border-top: 1px solid var(--border-color);
  display: flex;
  gap: 1rem;
  background: rgba(255, 255, 255, 0.05);
}

.message-input {
  flex: 1;
  padding: 0.75rem 1rem;
  border: 1px solid var(--border-color);
  border-radius: var(--radius-full);
  background: var(--card-bg);
  color: var(--text-primary);
  font-size: 1rem;
}

.message-input:focus {
  outline: none;
  border-color: var(--primary-color);
}

.send-button {
  padding: 0.75rem 1.5rem;
  background: var(--primary-color);
  color: var(--text-light);
  border: none;
  border-radius: var(--radius-full);
  cursor: pointer;
  transition: all 0.3s ease;
}

.send-button:hover {
  transform: translateY(-2px);
  box-shadow: 0 4px 12px rgba(0,0,0,0.1);
}

.features-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
  gap: 2rem;
  margin-top: 3rem;
}

.feature-card {
  background: var(--card-bg);
  border-radius: var(--radius-lg);
  padding: 2rem;
  text-align: center;
  transition: transform 0.3s ease;
  border: 1px solid var(--border-color);
}

.feature-card:hover {
  transform: translateY(-5px);
}

.feature-icon {
  font-size: 2.5rem;
  margin-bottom: 1rem;
}

.feature-card h3 {
  color: var(--text-primary);
  margin-bottom: 1rem;
}

.feature-card p {
  color: var(--text-secondary);
  line-height: 1.6;
}

@keyframes float {
  0%, 100% { transform: translate(0, 0); }
  25% { transform: translate(10px, -10px); }
  50% { transform: translate(-5px, 5px); }
  75% { transform: translate(5px, 10px); }
}

@keyframes fadeIn {
  from { opacity: 0; transform: translateY(10px); }
  to { opacity: 1; transform: translateY(0); }
}

@media (max-width: 768px) {
  .chat-container {
    height: 500px;
    margin: 0 1rem;
  }

  .features-grid {
    grid-template-columns: 1fr;
  }

  .message {
    max-width: 90%;
  }
}
</style>