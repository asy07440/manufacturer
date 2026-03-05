<template>
  <section class="how-it-works">
    <div class="container">
      <div class="text-center mb-10">
        <h2 class="section-title">How We Work</h2>
        <p class="section-subtitle">A simple three-step process to get your business moving forward with the right equipment.</p>
      </div>
      
      <div class="steps-grid">
        <div class="step-card">
          <div class="card-content">
            <div class="step-header">
              <span class="step-number">01</span>
              <h3 class="step-label">Request</h3>
            </div>
            <p class="step-description">
              Indicate what kind of machine you are interested in. Our team will review your requirements to find the perfect match.
            </p>
          </div>
          <div class="bg-number">01</div>
        </div>

        <div class="step-card">
          <div class="card-content">
            <div class="step-header">
              <span class="step-number">02</span>
              <h3 class="step-label">Development</h3>
            </div>
            <p class="step-description">
              You can give us a personal manager to make your application. We ensure every detail meets your operational standards.
            </p>
          </div>
          <div class="bg-number">02</div>
        </div>

        <div class="step-card">
          <div class="card-content">
            <div class="step-header">
              <span class="step-number">03</span>
              <h3 class="step-label">Installation</h3>
            </div>
            <p class="step-description">
              We install the machine with a comprehensive 1-year warranty period and technical support for your peace of mind.
            </p>
          </div>
          <div class="bg-number">03</div>
        </div>
      </div>
    </div>

    <div class="cta-banner">
      <div class="container cta-flex">
        <h2 class="cta-text">Up To 40% Off Our Most Popular Machines!</h2>
        <button class="cta-button">
          See Current Deals 
          <span class="arrow">→</span>
        </button>
      </div>
    </div>
  </section>
</template>

<style scoped>
/* Reset & Typography */
.how-it-works {
  font-family: 'Segoe UI', Roboto, Helvetica, Arial, sans-serif;
  background-color: #fcfdfe;
  padding-top: 50px;
  color: #334155;
}

.container {
  max-width: 1000px; /* Ukuran sedang/compact */
  margin: 0 auto;
  padding: 0 24px;
}

.text-center { text-align: center; }
.mb-10 { margin-bottom: 45px; }

/* Section Title & Subtitle */
.section-title {
  color: #1e293b;
  font-size: 1.75rem;
  font-weight: 700;
  margin-bottom: 10px;
}

.section-subtitle {
  color: #64748b;
  font-size: 0.95rem;
  max-width: 500px;
  margin: 0 auto;
}

/* Grid Layout */
.steps-grid {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 30px;
  padding-bottom: 60px;
}

/* Step Card Styles */
.step-card {
  position: relative;
  background: transparent;
  padding: 10px;
  transition: transform 0.3s ease;
}

.card-content {
  position: relative;
  z-index: 2;
}

.step-header {
  display: flex;
  align-items: center;
  gap: 8px;
  margin-bottom: 12px;
}

.step-number {
  color: #4f6ef7;
  font-weight: 800;
  font-size: 1rem;
}

.step-label {
  color: #1e293b;
  font-size: 1.1rem;
  font-weight: 700;
  margin: 0;
}

.step-description {
  color: #475569;
  line-height: 1.6;
  font-size: 0.88rem; /* Ukuran teks sedang */
  margin: 0;
}

/* Background Large Number */
.bg-number {
  position: absolute;
  top: -15px;
  left: -5px;
  font-size: 80px; /* Ukuran angka watermark sedang */
  font-weight: 900;
  color: rgba(79, 110, 247, 0.05);
  z-index: 1;
  pointer-events: none;
  user-select: none;
}

/* CTA Banner Styles */
.cta-banner {
  background-color: #5d78ff;
  padding: 30px 0;
}

.cta-flex {
  display: flex;
  justify-content: space-between;
  align-items: center;
  gap: 20px;
}

.cta-text {
  color: white;
  font-size: 1.4rem;
  font-weight: 600;
  margin: 0;
  letter-spacing: -0.02em;
}

.cta-button {
  background-color: transparent;
  color: white;
  white-space: nowrap;
  border: 1.5px solid rgba(255, 255, 255, 0.8);
  padding: 10px 22px;
  border-radius: 8px; /* Lebih modern/semi-rounded */
  font-size: 0.9rem;
  font-weight: 600;
  cursor: pointer;
  display: flex;
  align-items: center;
  gap: 8px;
  transition: all 0.2s ease;
}

.cta-button:hover {
  background-color: white;
  color: #5d78ff;
}

/* Responsive Design */
@media (max-width: 768px) {
  .steps-grid {
    grid-template-columns: 1fr;
    gap: 40px;
  }
  
  .cta-flex {
    flex-direction: column;
    text-align: center;
  }

  .section-title { font-size: 1.5rem; }
}
</style>