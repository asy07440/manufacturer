<template>
  <div class="contact-card-container">
    <div class="content-wrapper">
      
      <div class="info-section">
        <h2 class="title">Office Contacts</h2>
        <p class="subtitle">
          We envision a global textile industry that protects and restores the environment and enhances lives.
        </p>
        
        <div class="contact-list">
          <div class="contact-item">
            <MapPin class="icon-style" :size="20" />
            <div class="text-content">
              <p class="main-text">350 Flatbush ave New York</p>
              <p class="sub-text">NY 10018 USA.</p>
            </div>
          </div>

          <div class="contact-item">
            <Smartphone class="icon-style" :size="20" />
            <div class="text-content">
              <p class="sub-text">123-456-789</p>
              <p class="sub-text">234-432-456</p>
            </div>
          </div>
        </div>
      </div>

      <div class="map-section">
        <div class="map-canvas">
          <svg viewBox="0 0 400 250" class="dotted-svg">
            <pattern id="dotGrid" x="0" y="0" width="8" height="8" patternUnits="userSpaceOnUse">
              <circle cx="2" cy="2" r="1" fill="#cbd5e1" />
            </pattern>
            <rect width="100%" height="100%" fill="url(#dotGrid)" mask="url(#mapMask)" />
            <path id="mapMask" d="M50,50 L150,40 L250,45 L350,30 L380,100 L340,200 L200,220 L80,180 L40,120 Z" fill="white" />
          </svg>

          <MapPin class="pin pin-1" :size="18" />
          <MapPin class="pin pin-2" :size="18" />
          
          <div class="active-marker">
            <MapPin class="pin pin-active" :size="22" />
            <div class="popover-card">
              <h4 class="card-title">Factory 1</h4>
              <p class="card-desc">1504 Parrill Court, Crown Point IN, Indiana</p>
              <div class="card-footer">
                <p>219-616-6578</p>
                <p>219-765-9940</p>
              </div>
            </div>
          </div>
        </div>
      </div>

    </div>
  </div>
</template>

<script setup>
import { MapPin, Smartphone } from 'lucide-vue-next';
</script>

<style scoped>
/* Container Utama */
.contact-card-container {
  display: flex;
  justify-content: center;
  align-items: center;
  padding: 40px 20px;
  background-color: #fcfdfe;
}

.content-wrapper {
  display: grid;
  grid-template-columns: 1fr 1.2fr;
  gap: 30px;
  max-width: 900px; /* Ukuran sedang/compact */
  width: 100%;
  align-items: center;
}

/* Sisi Kiri */
.title {
  color: #2d3a5f;
  font-size: 1.75rem;
  font-weight: 700;
  margin-bottom: 12px;
}

.subtitle {
  color: #8c97ad;
  font-size: 0.95rem;
  line-height: 1.5;
  margin-bottom: 24px;
}

.contact-list {
  display: flex;
  flex-direction: column;
  gap: 16px;
}

.contact-item {
  display: flex;
  gap: 12px;
  align-items: flex-start;
}

.icon-style {
  color: #818cf8;
  flex-shrink: 0;
}

.main-text {
  font-weight: 600;
  color: #475569;
  font-size: 0.9rem;
  margin: 0;
}

.sub-text {
  color: #94a3b8;
  font-size: 0.85rem;
  margin: 2px 0 0 0;
}

/* Sisi Kanan (Peta) */
.map-section {
  position: relative;
}

.map-canvas {
  position: relative;
  width: 100%;
  height: 250px;
}

.dotted-svg {
  width: 100%;
  height: 100%;
  opacity: 0.6;
}

/* Pin Styling */
.pin {
  position: absolute;
  color: #cbd5e1;
}

.pin-1 { top: 20%; left: 20%; }
.pin-2 { top: 15%; right: 25%; }

.active-marker {
  position: absolute;
  bottom: 35%;
  right: 30%;
}

.pin-active {
  color: #3b82f6;
  filter: drop-shadow(0 2px 4px rgba(59, 130, 246, 0.3));
}

/* Popover Card */
.popover-card {
  position: absolute;
  left: 28px;
  top: -10px;
  background: white;
  padding: 16px;
  border-radius: 10px;
  box-shadow: 0 10px 25px rgba(0, 0, 0, 0.08);
  width: 190px;
  border: 1px solid #f1f5f9;
  z-index: 5;
}

.card-title {
  color: #4f46e5;
  font-size: 0.9rem;
  font-weight: 700;
  margin: 0 0 8px 0;
}

.card-desc {
  color: #64748b;
  font-size: 0.75rem;
  line-height: 1.3;
  margin-bottom: 10px;
}

.card-footer p {
  color: #94a3b8;
  font-size: 0.75rem;
  margin: 1px 0;
}

/* Responsif untuk layar kecil */
@media (max-width: 768px) {
  .content-wrapper {
    grid-template-columns: 1fr;
    gap: 40px;
  }
  
  .popover-card {
    width: 160px;
    left: 20px;
  }
}
</style>