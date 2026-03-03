<template>
  <div class="page-wrapper">
    <section class="section">
      <div class="container">
        <header class="section-header-compact">
          <h2 class="section-title">Industries We Serve</h2>
          <p class="section-subtitle">
            Manufacturer's high end manufacturing services are a perfect
            complement to today's high tech industries.
          </p>
        </header>

        <div class="industry-grid">
          <div
            v-for="item in industries"
            :key="item.title"
            class="industry-card"
          >
            <div class="card-inner">
              <div class="icon-box">
                <component :is="item.icon" :size="32" stroke-width="1.5" />
              </div>
              <div class="card-info">
                <h3 class="card-title">{{ item.title }}</h3>
                <p class="card-text">{{ item.desc }}</p>
                <a href="#" class="link-more">LEARN MORE <ArrowRight :size="14" /></a>
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>

    <section class="section bg-light">
      <div class="container">
        <header class="section-header-compact">
          <h2 class="section-title">Our Production</h2>
          <p class="section-subtitle">
            The manufacture of industrial equipment requires a vast knowledge base of processes.
          </p>
        </header>

        <div class="production-grid">
          <div v-for="prod in production" :key="prod.name" class="prod-card">
            <img :src="prod.img" :alt="prod.name" class="prod-bg" />
            <div class="prod-overlay"></div>
            <div class="prod-content">
              <component :is="prod.icon" :size="24" color="white" />
              <h4 class="prod-name">{{ prod.name }}</h4>
            </div>
          </div>
        </div>

        <div class="action-area">
          <button class="btn-primary-sm">
            Download PDF <ArrowRight :size="16" />
          </button>
        </div>
      </div>
    </section>
  </div>
</template>

<script setup>
import {
  Hammer, Factory, Component as ComponentIcon,
  Drill, Scissors, Layers, Cog, ArrowRight, Maximize,
} from "lucide-vue-next";

const industries = [
  { title: "Woodworking", icon: Factory, desc: "Whether you're managing around-the-clock production or working on a project..." },
  { title: "Metalworking", icon: ComponentIcon, desc: "From our versatile ironworkers to our easily-programmable plasma tables..." },
  { title: "Stone Cutting", icon: Hammer, desc: "We build machines that set the industry standard for precision and durability..." },
];

const production = [
  { name: "Tube Benders", icon: Cog, img: "https://images.unsplash.com/photo-1537462715879-360eeb61a0ad?q=80&w=400" },
  { name: "Band Saws", icon: Scissors, img: "https://images.unsplash.com/photo-1504917595217-d4dc5ebe6122?q=80&w=400" },
  { name: "Metal Press", icon: Layers, img: "https://images.unsplash.com/photo-1581092160562-40aa08e78837?q=80&w=400" },
  { name: "Plasma Tables", icon: Maximize, img: "https://images.unsplash.com/photo-1565043589221-1a6fd9ae45c7?q=80&w=400" },
  { name: "Sheet Metal", icon: Layers, img: "https://images.unsplash.com/photo-1513828583688-c52646db42da?q=80&w=400" },
  { name: "Metal Drills", icon: Drill, img: "https://images.unsplash.com/photo-1513828583688-c52646db42da?q=80&w=400" },
];
</script>

<style scoped>
.page-wrapper {
  font-family: "Inter", system-ui, sans-serif;
  color: #334155;
}

.container {
  max-width: 1000px; /* Diperkecil dari 1140px */
  margin: 0 auto;
  padding: 0 20px;
}

.section {
  padding: 60px 0; /* Padding vertikal dikurangi dari 100px */
}

.bg-light { background-color: #f8fafc; }

/* Header Compact */
.section-header-compact {
  margin-bottom: 40px;
  text-align: left; /* Berubah jadi rata kiri agar lebih compact */
  border-left: 4px solid #6366f1;
  padding-left: 20px;
}

.section-title {
  font-size: 24px; /* Dikecilkan dari 32px */
  font-weight: 800;
  color: #0f172a;
  margin: 0 0 8px 0;
}

.section-subtitle {
  font-size: 14px;
  color: #64748b;
  max-width: 600px;
  margin: 0;
}

/* Industry Grid Compact */
.industry-grid {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 20px;
}

.industry-card {
  background: white;
  border: 1px solid #e2e8f0;
  border-radius: 12px;
  padding: 20px;
  transition: all 0.3s ease;
}

.industry-card:hover {
  box-shadow: 0 10px 20px rgba(0,0,0,0.05);
  border-color: #6366f1;
}

.icon-box {
  color: #6366f1;
  margin-bottom: 15px;
}

.card-title {
  font-size: 16px; /* Lebih kecil & tebal */
  font-weight: 700;
  margin-bottom: 8px;
  color: #1e293b;
}

.card-text {
  font-size: 13px;
  color: #64748b;
  line-height: 1.4;
  margin-bottom: 15px;
}

.link-more {
  font-size: 11px;
  font-weight: 800;
  color: #6366f1;
  text-decoration: none;
  display: inline-flex;
  align-items: center;
  gap: 4px;
}

/* Production Grid Compact */
.production-grid {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 15px; /* Jarak antar gambar dipersempit */
}

.prod-card {
  position: relative;
  height: 160px; /* Tinggi dikurangi dari 240px */
  border-radius: 8px;
  overflow: hidden;
}

.prod-bg {
  width: 100%;
  height: 100%;
  object-fit: cover;
}

.prod-overlay {
  position: absolute;
  inset: 0;
  background: rgba(15, 23, 42, 0.6);
  transition: 0.3s;
}

.prod-card:hover .prod-overlay { background: rgba(99, 102, 241, 0.8); }

.prod-content {
  position: absolute;
  inset: 0;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  z-index: 2;
  padding: 10px;
}

.prod-name {
  color: white;
  margin-top: 8px;
  font-weight: 600;
  font-size: 14px;
  text-align: center;
}

/* Button Small */
.action-area { text-align: center; margin-top: 30px; }

.btn-primary-sm {
  background: #6366f1;
  color: white;
  border: none;
  padding: 10px 24px;
  border-radius: 6px;
  font-size: 14px;
  font-weight: 600;
  cursor: pointer;
  display: inline-flex;
  align-items: center;
  gap: 8px;
}

@media (max-width: 768px) {
  .industry-grid, .production-grid { grid-template-columns: 1fr 1fr; }
}

@media (max-width: 480px) {
  .industry-grid, .production-grid { grid-template-columns: 1fr; }
}
</style>