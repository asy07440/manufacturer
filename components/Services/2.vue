<template>
  <section class="capabilities-wrapper">
    <div class="grid-row">
      <div class="text-content">
        <h2 class="main-title">Our Capabilities</h2>
        <p class="accent-text">
          Stop by today; our talented staff will be happy to help you find what
          you're searching for!
        </p>
        <p class="ceo-label">CEO: Steven Rogers</p>
      </div>
      <div class="image-content">
        <img
          src="https://images.unsplash.com/photo-1522202176988-66273c2fd55f?q=80&w=1000&auto=format&fit=crop"
          alt="Office Collaboration"
        />
      </div>
    </div>

    <div class="grid-row reverse">
      <div class="image-content">
        <img
          src="https://images.unsplash.com/photo-1573497019940-1c28c88b4f3e?q=80&w=1000&auto=format&fit=crop"
          alt="Professional Meeting"
        />
      </div>
      <div class="text-content">
        <h2 class="main-title">How we do it</h2>
        <div class="description-block">
          <p>
            Textile engages and catalyzes the textile industry across the supply
            chain through partnerships and collaborations, building knowledge
            and capacity to inform and educate. We further leverage our
            influence to create action, change and collective impact.
          </p>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
/* Container & Global Style */
.capabilities-wrapper {
  max-width: 1100px; /* Ukuran lebih compact */
  margin: 0 auto;
  font-family:
    "Inter",
    -apple-system,
    BlinkMacSystemFont,
    "Segoe UI",
    sans-serif;
  background-color: #fff;
}

/* Grid System */
.grid-row {
  display: grid;
  grid-template-columns: 1fr 1fr;
  align-items: stretch;
}

/* Konten Teks */
.text-content {
  padding: 50px 60px; /* Padding yang presisi agar terlihat padat */
  display: flex;
  flex-direction: column;
  justify-content: center;
}

/* Gambar */
.image-content {
  height: 400px; /* Tinggi dikunci agar seragam */
  overflow: hidden;
}

.image-content img {
  width: 100%;
  height: 100%;
  object-fit: cover;
  display: block;
}

/* Typography */
.main-title {
  font-size: 2.25rem; /* Ukuran besar sesuai permintaan */
  font-weight: 850; /* Sangat tebal (Heavy) */
  color: #1e293b;
  margin-bottom: 24px;
  letter-spacing: -0.02em;
}

.accent-text {
  font-size: 1.15rem;
  line-height: 1.6;
  color: #3b82f6; /* Warna biru sesuai gambar */
  margin-bottom: 20px;
  font-weight: 500;
}

.ceo-label {
  font-size: 1rem;
  color: #64748b;
  font-weight: 600;
}

.description-block p {
  font-size: 1.05rem;
  line-height: 1.7;
  color: #475569;
  margin-bottom: 18px;
}

/* Logic untuk membalik baris kedua */
.reverse .image-content {
  order: 1;
}
.reverse .text-content {
  order: 2;
}

/* Responsive */
@media (max-width: 900px) {
  .grid-row {
    grid-template-columns: 1fr;
  }

  .grid-row.reverse {
    display: flex;
    flex-direction: column; /* Gambar tetap di atas pada mobile */
  }

  .text-content {
    padding: 40px 24px;
    order: 2 !important;
  }

  .image-content {
    height: 300px;
    order: 1 !important;
  }

  .main-title {
    font-size: 1.8rem;
  }
}
</style>
