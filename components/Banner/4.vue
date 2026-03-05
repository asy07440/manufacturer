<template>
  <section class="capabilities-section">
    <div class="container">
      
      <div class="content-wrapper">
        
        <div class="image-column">
          <div class="dot-pattern"></div>
          <div class="image-container">
            <img 
              src="https://images.unsplash.com/photo-1537462715879-360eeb61a0ad?q=80&w=400" 
              alt="Manufacturing Capabilities" 
              class="main-image" 
            />
          </div>
        </div>

        <div class="text-column">
          <h2 class="section-title">Our Capabilities</h2>
          
          <p class="section-description">
            We are restocking as quickly as possible to meet the incredible demand. Come back on 7/30 to order more of these exclusive flavors inspired by the places you call home. 
            <br><br>
            Our dedicated team is working around the clock to ensure the highest quality in every batch, combining precision engineering with unparalleled craftsmanship to bring you an unforgettable experience.
          </p>
          
          <img 
            src="https://placehold.co/180x70/f8f9fc/000?text=Signature" 
            alt="Signature" 
            class="signature-img" 
          />
          
          <NuxtLink to="#" class="btn-primary">
            Learn More
            <ArrowRight :size="18" class="arrow-icon" />
          </NuxtLink>
        </div>
      </div>

      <div class="logo-row">
        <div v-for="(logo, index) in logos" :key="index" class="logo-card">
          <img :src="logo.src" :alt="logo.alt" />
        </div>
      </div>

    </div>
  </section>
</template>

<script setup lang="ts">
// Import Lucide Icons
import { ArrowRight } from 'lucide-vue-next';

const logos = [
  { src: 'https://placehold.co/130x40/FFF/000?text=CHELSEA+LEIFKEN', alt: 'Chelsea Leifken' },
  { src: 'https://placehold.co/130x40/FFF/000?text=PAGE+THIRTY', alt: 'Page Thirty' },
  { src: 'https://placehold.co/130x40/FFF/000?text=Rick+Owens', alt: 'Rick Owens' },
  { src: 'https://placehold.co/130x40/FFF/000?text=BERGDORF+GOODMAN', alt: 'Bergdorf Goodman' },
  { src: 'https://placehold.co/130x40/FFF/000?text=GORDON+RAMSAY', alt: 'Gordon Ramsay Group' },
];
</script>

<style scoped>
/* --- Variabel Warna & Font --- */
.capabilities-section {
  --bg-color: #f8f9fc;
  --text-dark: #2d3154;
  --text-light: #6a76a5;
  --primary-blue: #5b6af0;
  --primary-blue-hover: #4a57d4;
  --dot-color: #c4caeb;

  background-color: var(--bg-color);
  padding: 60px 20px;
  font-family: 'Inter', sans-serif;
  overflow: hidden;
}

.container {
  max-width: 1050px;
  margin: 0 auto;
}

/* --- Content Wrapper --- */
.content-wrapper {
  display: flex;
  flex-direction: column;
  gap: 40px;
  margin-bottom: 50px;
  align-items: center;
}

@media (min-width: 860px) {
  .content-wrapper {
    flex-direction: row;
    justify-content: space-between;
    gap: 60px;
  }
}

/* --- Gambar (Compact Medium) --- */
.image-column {
  flex: 1;
  position: relative;
  width: 100%;
  max-width: 400px; /* Diperkecil sedikit agar lebih compact */
}

.dot-pattern {
  position: absolute;
  left: -25px;
  bottom: -25px;
  width: 120px;
  height: 120px;
  z-index: 1;
  background-image: radial-gradient(var(--dot-color) 2px, transparent 2px);
  background-size: 18px 18px;
}

.image-container {
  position: relative;
  z-index: 2;
  border-radius: 8px;
  overflow: hidden;
  box-shadow: 0 10px 25px rgba(0, 0, 0, 0.08);
  aspect-ratio: 1 / 1;
}

.main-image {
  width: 100%;
  height: 100%;
  object-fit: cover;
  display: block;
}

/* --- Teks & Deskripsi --- */
.text-column {
  flex: 1;
  display: flex;
  flex-direction: column;
  align-items: flex-start;
  max-width: 520px;
}

.section-title {
  color: var(--text-dark);
  font-size: 2rem;
  font-weight: 700;
  margin-bottom: 16px;
  letter-spacing: -0.02em;
}

.section-description {
  color: var(--text-light);
  font-size: 0.95rem; /* Ukuran teks sedang/rapi */
  line-height: 1.6;
  margin-bottom: 24px;
}

.signature-img {
  max-width: 120px;
  margin-bottom: 25px;
  mix-blend-mode: multiply;
  opacity: 0.9;
}

/* --- Button Lucide --- */
.btn-primary {
  display: inline-flex;
  align-items: center;
  gap: 10px;
  background-color: var(--primary-blue);
  color: #ffffff;
  padding: 10px 24px;
  border-radius: 30px;
  text-decoration: none;
  font-size: 0.9rem;
  font-weight: 600;
  transition: all 0.3s ease;
  box-shadow: 0 4px 12px rgba(91, 106, 240, 0.2);
}

.btn-primary:hover {
  background-color: var(--primary-blue-hover);
  transform: translateY(-2px);
  box-shadow: 0 6px 16px rgba(91, 106, 240, 0.3);
}

.arrow-icon {
  transition: transform 0.3s ease;
}

.btn-primary:hover .arrow-icon {
  transform: translateX(4px);
}

/* --- Logo Section (Compact) --- */
.logo-row {
  display: flex;
  flex-wrap: wrap;
  gap: 12px;
  justify-content: center;
}

@media (min-width: 860px) {
  .logo-row {
    justify-content: space-between;
    flex-wrap: nowrap;
  }
}

.logo-card {
  background-color: #ffffff;
  padding: 12px 18px;
  border-radius: 6px;
  display: flex;
  align-items: center;
  justify-content: center;
  width: calc(50% - 6px);
  height: 70px;
  box-shadow: 0 2px 5px rgba(0, 0, 0, 0.02);
  transition: all 0.3s ease;
}

.logo-card:hover {
  transform: scale(1.02);
  box-shadow: 0 4px 12px rgba(0, 0, 0, 0.05);
}

@media (min-width: 860px) {
  .logo-card {
    width: 100%;
    max-width: 180px;
  }
}

.logo-card img {
  max-width: 100%;
  max-height: 32px;
  object-fit: contain;
  filter: grayscale(100%);
  opacity: 0.5;
  transition: all 0.4s ease;
}

.logo-card:hover img {
  filter: grayscale(0%);
  opacity: 1;
}
</style>