<template>
  <div class="main-layout">
    <Header />
    
    <main class="container">
      <NuxtPage :transition="{
        name: 'page',
        mode: 'out-in'
      }" />
    </main>

  </div>
</template>

<script setup>
import Header from '@/components/Header.vue'
import Footer from '@/components/Footer.vue'
import { onMounted } from 'vue';

// Smooth page transition styles
const route = useRoute()

onMounted(() => {
  document.body.classList.add('loaded');
});
</script>

<style scoped>
.main-layout {
  display: flex;
  flex-direction: column;
  min-height: 100vh;
}

main {
  flex: 1;
  padding-top: var(--space-xl);
  padding-bottom: var(--space-xl);
}

/* Page transition animations */
.page-enter-active,
.page-leave-active {
  transition: all var(--transition-normal);
}

.page-enter-from,
.page-leave-to {
  opacity: 0;
  transform: translateY(10px);
}
</style>
