<template>
  <section class="services-container">
    <div class="services-grid">
      <div v-for="item in services" :key="item.title" class="card">
        <div class="icon-wrapper">
          <component :is="item.icon" :size="48" stroke-width="1.5" />
        </div>

        <h2 class="card-title">{{ item.title }}</h2>
        
        <p class="card-text">
          {{ item.description }}
        </p>

        <NuxtLink to="/" class="learn-more">
          <span class="line"></span>
          LEARN MORE
        </NuxtLink>
      </div>
    </div>
  </section>
</template>

<script setup>
// Import icon dari lucide-vue-next
import { HardHat, Factory, Drill } from 'lucide-vue-next'

const services = [
  {
    title: 'Woodworking',
    description: "Whether you're managing around-the-clock production or working on a project that requires unique precision, our machines deliver.",
    icon: HardHat // Ganti dengan icon yang sesuai keinginan
  },
  {
    title: 'Metalworking',
    description: 'From our versatile ironworkers to our easily-programmable plasma tables, we provide the tools to shape the future of your shop.',
    icon: Factory
  },
  {
    title: 'Stone Cutting',
    description: 'We build machines that set the industry standard for precision and durability, ensuring every cut is perfect for your masonry needs.',
    icon: Drill
  }
]
</script>

<style scoped>
/* Reset & Container */
.services-container {
  display: flex;
  justify-content: center;
  align-items: center;
  padding: 80px 24px;
  background-color: #ffffff;
  font-family: 'Inter', -apple-system, BlinkMacSystemFont, sans-serif;
}

/* Grid Layout - Compact & Balanced */
.services-grid {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 60px;
  max-width: 1200px;
  width: 100%;
}

/* Card Styling */
.card {
  display: flex;
  flex-direction: column;
  align-items: center;
  text-align: center;
}

/* Icon Styling */
.icon-wrapper {
  color: #3b82f6; /* Blue-500 */
  margin-bottom: 32px;
  transition: transform 0.3s ease;
}

.card:hover .icon-wrapper {
  transform: translateY(-5px);
}

/* Typography - Bold & Readable */
.card-title {
  font-size: 1.75rem; /* Ukuran lebih mantap */
  font-weight: 800;
  color: #1e293b;
  margin-bottom: 20px;
  letter-spacing: -0.025em;
}

.card-text {
  font-size: 1.05rem; /* Teks tidak dikurangi, justru diperjelas */
  line-height: 1.7;
  color: #64748b;
  margin-bottom: 32px;
  max-width: 340px;
  font-weight: 450;
}

/* Button / Link Styling */
.learn-more {
  display: flex;
  align-items: center;
  gap: 12px;
  font-size: 0.85rem;
  font-weight: 800;
  color: #3b82f6;
  text-decoration: none;
  letter-spacing: 0.1em;
  transition: all 0.2s ease;
}

.line {
  height: 2px;
  width: 20px;
  background-color: #3b82f6;
  transition: width 0.3s ease;
}

.learn-more:hover {
  color: #2563eb;
}

.learn-more:hover .line {
  width: 35px;
}

/* Responsive */
@media (max-width: 1024px) {
  .services-grid {
    gap: 30px;
  }
}

@media (max-width: 768px) {
  .services-grid {
    grid-template-columns: 1fr;
    gap: 60px;
  }
  
  .services-container {
    padding: 60px 20px;
  }
}
</style>