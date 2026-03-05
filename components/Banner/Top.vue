<script setup>
/**
 * Banner Top Component - Clean & Compact Version
 * Props:
 * - title: Judul manual (opsional)
 * - bgImage: URL gambar latar (opsional)
 */
const props = defineProps({
  title: { type: String, default: '' },
  bgImage: { type: String, default: 'https://images.unsplash.com/photo-1497366216548-37526070297c?auto=format&fit=crop&q=80&w=1600' }
});

const route = useRoute();

// Mengambil Nama Halaman dari Meta (definePageMeta) atau Nama Route
const pageTitle = computed(() => {
  return props.title || route.meta.title || route.name || 'Halaman';
});

// Breadcrumb logic: Home -> Current Page Name
const breadcrumbs = computed(() => [
  { name: 'Home', path: '/' },
  { name: pageTitle.value, path: route.path }
]);
</script>

<template>
  <header class="banner-container" :style="{ backgroundImage: `url(${bgImage})` }">
    <div class="banner-overlay">
      <div class="banner-content">
        <h1 class="banner-title">{{ pageTitle }}</h1>
        
        <nav class="breadcrumb-wrapper">
          <ul class="breadcrumb-list">
            <li v-for="(item, index) in breadcrumbs" :key="index" class="breadcrumb-item">
              <NuxtLink v-if="index === 0" :to="item.path" class="breadcrumb-link">
                {{ item.name }}
              </NuxtLink>
              <span v-else class="breadcrumb-current">{{ item.name }}</span>
              
              <span v-if="index === 0" class="breadcrumb-sep">
                <svg viewBox="0 0 24 24" width="14" height="14" fill="none" stroke="currentColor" stroke-width="2.5">
                  <path d="M9 18l6-6-6-6" />
                </svg>
              </span>
            </li>
          </ul>
        </nav>
      </div>
    </div>
  </header>
</template>

<style scoped>
/* Reset & Base */
.banner-container {
  position: relative;
  width: 100%;
  height: 220px; /* Tinggi sedang/compact */
  background-size: cover;
  background-position: center;
  background-repeat: no-repeat;
  display: flex;
  align-items: center;
  overflow: hidden;
}

/* Overlay Putih Halus (Semi-Transparan) */
.banner-overlay {
  position: absolute;
  inset: 0;
  background-color: rgba(255, 255, 255, 0.88); 
  backdrop-filter: blur(2px); /* Memberikan kesan modern */
  display: flex;
  align-items: center;
  justify-content: center;
}

.banner-content {
  text-align: center;
  z-index: 10;
  padding: 0 20px;
}

.banner-title {
  font-family: 'Inter', -apple-system, BlinkMacSystemFont, sans-serif;
  font-size: 2.5rem;
  font-weight: 800;
  color: #1a2a4e; /* Navy gelap yang elegan */
  margin-bottom: 8px;
  letter-spacing: -0.03em;
}

/* Breadcrumb Styling */
.breadcrumb-list {
  list-style: none;
  display: inline-flex;
  align-items: center;
  padding: 0;
  margin: 0;
}

.breadcrumb-item {
  display: flex;
  align-items: center;
  font-family: 'Inter', sans-serif;
  font-size: 0.95rem;
}

.breadcrumb-link {
  color: #8c98a4;
  text-decoration: none;
  transition: color 0.2s ease;
}

.breadcrumb-link:hover {
  color: #3b82f6; /* Warna accent biru */
}

.breadcrumb-current {
  color: #a0aec0;
  font-weight: 500;
}

.breadcrumb-sep {
  display: flex;
  align-items: center;
  margin: 0 10px;
  color: #cbd5e0;
}

/* Responsive Scaling */
@media (max-width: 768px) {
  .banner-container {
    height: 180px;
  }
  .banner-title {
    font-size: 2rem;
  }
}
</style>