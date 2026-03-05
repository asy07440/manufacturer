<template>
  <div class="stats-wrapper">
    <div class="container">
      <div class="brand-row">
        <div v-for="(brand, index) in brands" :key="index" class="brand-item">
          <div class="brand-inner">
            <component :is="brand.icon" :size="20" stroke-width="1.5" class="brand-icon" />
            <span class="brand-text">{{ brand.name }}</span>
          </div>
        </div>
      </div>

      <div class="stats-grid">
        <div v-for="(stat, index) in statistics" :key="index" class="stat-card">
          <div class="stat-icon-wrapper">
            <component :is="stat.icon" :size="28" stroke-width="2" />
          </div>
          <div class="stat-content">
            <h2 class="stat-value">{{ stat.value }}</h2>
            <p class="stat-label">{{ stat.label }}</p>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
import { 
  Box, 
  Cpu, 
  Layers, 
  Zap, 
  Hexagon, 
  BarChart3, 
  LayoutGrid, 
  Rocket, 
  Shirt 
} from 'lucide-vue-next';

const brands = [
  { name: 'Volker Stevin', icon: Hexagon },
  { name: 'KPHONE', icon: Box },
  { name: 'EDTECH', icon: Cpu },
  { name: 'FAST Brothers', icon: Layers },
  { name: 'TVC', icon: Zap },
];

const statistics = [
  { value: '37,500', label: 'Tons of yarn', icon: BarChart3 },
  { value: '17,000', label: 'Tons of knitted fabric', icon: LayoutGrid },
  { value: '9,000', label: 'Tons of dyed fabric', icon: Rocket },
  { value: '1,400', label: 'Tons ready-made clothes', icon: Shirt },
];
</script>

<style scoped>
/* Reset & Base */
.stats-wrapper {
  width: 100%;
  background-color: #fcfcff;
  padding: 60px 0;
  font-family: 'Inter', -apple-system, sans-serif;
}

.container {
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 24px;
}

/* --- Brand Row Styling --- */
.brand-row {
  display: flex;
  justify-content: space-between;
  align-items: center;
  gap: 16px;
  margin-bottom: 60px;
  flex-wrap: wrap;
}

.brand-item {
  flex: 1;
  min-width: 180px;
}

.brand-inner {
  background: white;
  padding: 16px;
  border-radius: 4px;
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 10px;
  box-shadow: 0 4px 12px rgba(0, 0, 0, 0.03);
  transition: transform 0.2s ease, box-shadow 0.2s ease;
  border: 1px solid #f0f0f5;
}

.brand-inner:hover {
  transform: translateY(-2px);
  box-shadow: 0 6px 16px rgba(0, 0, 0, 0.06);
}

.brand-icon { color: #a0a0a0; }
.brand-text {
  font-size: 0.8rem;
  font-weight: 700;
  color: #444;
  text-transform: uppercase;
  letter-spacing: 0.5px;
}

/* --- Stats Grid Styling --- */
.stats-grid {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  gap: 32px;
}

.stat-card {
  display: flex;
  align-items: flex-start;
  gap: 16px;
}

.stat-icon-wrapper {
  color: #5d5fef;
  background: #f0f2ff;
  padding: 8px;
  border-radius: 8px;
  display: flex;
  align-items: center;
  justify-content: center;
  transition: background 0.3s ease;
}

.stat-card:hover .stat-icon-wrapper {
  background: #e5e8ff;
}

.stat-content {
  display: flex;
  flex-direction: column;
}

.stat-value {
  margin: 0;
  font-size: 1.85rem;
  font-weight: 800;
  color: #1a1a1b;
  line-height: 1.1;
}

.stat-label {
  margin: 6px 0 0;
  font-size: 0.95rem;
  color: #6b7280;
  font-weight: 500;
}

/* --- Responsivitas --- */
@media (max-width: 1024px) {
  .stats-grid {
    grid-template-columns: repeat(2, 1fr);
    row-gap: 40px;
  }
}

@media (max-width: 640px) {
  .brand-row {
    justify-content: center;
  }
  .brand-item {
    min-width: 45%;
  }
  .stats-grid {
    grid-template-columns: 1fr;
  }
  .stat-card {
    justify-content: flex-start;
    padding-left: 20%;
  }
}
</style>