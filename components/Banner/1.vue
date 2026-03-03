<template>
  <section class="hero-compact">
    <div class="dots-bg"></div>

    <div class="container">
      <div class="hero-grid">
        <div class="hero-text">
          <div class="badge">Industrial Solutions</div>
          <h1>
            Expert Technical Support<br />
            High-Performance Machines<br />
            Profitable Solutions
          </h1>
          <p class="subtitle">Custom Solutions to Suit Your Need</p>
          
          <div class="btn-row">
            <button class="btn-main">
              In Details <span class="arrow">→</span>
            </button>
            <button class="btn-outline">
              Get a Quote <span class="arrow">→</span>
            </button>
          </div>
        </div>

        <div class="hero-visual">
          <img 
            src="https://images.unsplash.com/photo-1486406146926-c627a92ad1ab?q=80&w=1000&auto=format&fit=crop" 
            alt="Industrial"
            class="visual-img"
          />
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
.hero-compact {
  position: relative;
  background-color: #fff;
  overflow: hidden;
  padding: 40px 0; /* Padding dikurangi */
}

.container {
  max-width: 1100px; /* Lebar maksimal dipersempit */
  margin: 0 auto;
  padding: 0 24px;
}

.hero-grid {
  display: grid;
  grid-template-columns: 1.1fr 0.9fr;
  align-items: center;
  gap: 40px;
}

/* Tipografi yang lebih sedang */
.badge {
  color: #5a73f8;
  font-size: 0.85rem;
  font-weight: 700;
  text-transform: uppercase;
  letter-spacing: 1px;
  margin-bottom: 12px;
}

h1 {
  font-size: 2.25rem; /* Dikecilkan dari 3.5rem */
  font-weight: 800;
  line-height: 1.2;
  color: #2d3e66;
  margin: 0 0 16px 0;
}

.subtitle {
  font-size: 1.05rem; /* Dikecilkan */
  color: #64748b;
  margin-bottom: 24px;
}

/* Tombol lebih ringkas */
.btn-row {
  display: flex;
  gap: 12px;
}

.btn-main, .btn-outline {
  padding: 10px 22px; /* Lebih kecil */
  border-radius: 8px;
  font-weight: 600;
  font-size: 0.9rem;
  cursor: pointer;
  transition: all 0.2s;
  display: flex;
  align-items: center;
  gap: 8px;
}

.btn-main {
  background: #5a73f8;
  color: white;
  border: none;
}

.btn-outline {
  background: transparent;
  color: #5a73f8;
  border: 1px solid #5a73f8;
}

.btn-main:hover { background: #4359d6; }

/* Gambar dengan proporsi terkontrol */
.hero-visual {
  position: relative;
  height: 380px; /* Tinggi dibatasi */
}

.visual-img {
  width: 100%;
  height: 100%;
  object-fit: cover;
  border-radius: 12px;
  clip-path: polygon(15% 0%, 100% 0%, 100% 100%, 0% 100%);
}

/* Pattern latar belakang */
.dots-bg {
  position: absolute;
  top: 0; left: 0;
  width: 200px;
  height: 200px;
  background-image: radial-gradient(#e2e8f0 2px, transparent 2px);
  background-size: 20px 20px;
  z-index: 0;
}

/* Responsive */
@media (max-width: 850px) {
  .hero-grid {
    grid-template-columns: 1fr;
    text-align: center;
  }
  .btn-row { justify-content: center; }
  .hero-visual { display: none; } /* Sembunyikan gambar di layar kecil agar hemat ruang */
  h1 { font-size: 1.8rem; }
}
</style>