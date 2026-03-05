<template>
  <div class="page-container">
    <div class="content-wrapper">
      
      <section class="compact-section">
        <div class="media-box">
          <img src="https://images.unsplash.com/photo-1504148455328-c376907d081c?q=80&w=800" alt="Workplace" />
        </div>
        <div class="text-box">
          <h2 class="title">Welcome</h2>
          <p class="description">
            Textile is a global non-profit that works closely with our members to drive industry transformation in preferred fibers, integrity and standards and responsible supply networks. We identify and share best practices regarding farming, materials, processing, and traceability to reduce the textile industry's impact.
          </p>
        </div>
      </section>

      <section class="compact-section reverse">
        <div class="media-box">
          <img src="https://images.unsplash.com/photo-1522202176988-66273c2fd55f?q=80&w=800" alt="Team" />
        </div>
        <div class="text-box">
          <h2 class="title">Founder’s Note</h2>
          <p class="description">
            Members may be new to sustainability practices or want to take their strategy to the next level. We provide the tools and network to make that transition seamless and impactful.
          </p>
          <p class="role-text">CEO: Steven Rogers</p>
        </div>
      </section>

    </div>
  </div>
</template>

<style scoped>
/* Container Utama */
.page-container {
  font-family: 'Inter', -apple-system, sans-serif;
  display: flex;
  justify-content: center;
  padding: 40px 20px;
  background-color: #fcfcfc;
  color: #333;
}

.content-wrapper {
  max-width: 900px; /* Lebar compact */
  width: 100%;
}

/* Layout Grid Compact */
.compact-section {
  display: flex;
  align-items: center;
  gap: 40px;
  margin-bottom: 60px; /* Jarak antar section yang pas */
}

.compact-section.reverse {
  flex-direction: row-reverse;
}

/* Media/Image Box */
.media-box {
  flex: 1;
  max-width: 450px;
}

.media-box img {
  width: 100%;
  height: 280px; /* Ukuran tinggi foto dikunci agar compact */
  object-fit: cover;
  border-radius: 10px;
  box-shadow: 0 8px 24px rgba(0, 0, 0, 0.06);
  display: block;
}

/* Text Box */
.text-box {
  flex: 1;
}

.title {
  font-size: 1.75rem;
  font-weight: 700;
  color: #1a202c;
  margin-bottom: 12px;
  letter-spacing: -0.02em;
}

.description {
  font-size: 0.95rem;
  line-height: 1.6;
  color: #4a5568;
  margin-bottom: 15px;
}

.role-text {
  font-weight: 600;
  font-size: 0.9rem;
  color: #718096;
}

/* Responsive (Mobile) */
@media (max-width: 768px) {
  .compact-section, .compact-section.reverse {
    flex-direction: column;
    gap: 20px;
    margin-bottom: 40px;
  }
  
  .media-box {
    max-width: 100%;
  }

  .media-box img {
    height: 220px;
  }

  .text-box {
    text-align: center;
  }
}
</style>