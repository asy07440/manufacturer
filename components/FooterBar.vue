<template>
  <footer class="footer-section">
    <div class="container">
      <div class="footer-grid">
        
        <div class="footer-col branding">
          <h2 class="copyright-text">2020 MANUFACTURER<br>ALL RIGHTS RESERVED</h2>
          <p class="theme-info">
            Manufacturer – <span class="highlight">Factory, Industrial, Manufacturing</span> WordPress Theme
          </p>
          <div class="social-icons">
            <a href="#" class="icon-link"><Facebook :size="20" /></a>
            <a href="#" class="icon-link"><Twitter :size="20" /></a>
            <a href="#" class="icon-link"><Youtube :size="20" /></a>
            <a href="#" class="icon-link"><Instagram :size="20" /></a>
          </div>
        </div>

        <div class="footer-col">
          <h3>Company</h3>
          <ul>
            <li><NuxtLink to="/">Home</NuxtLink></li>
            <li><NuxtLink to="/">Our factories</NuxtLink></li>
            <li><NuxtLink to="/">Mission and strategy</NuxtLink></li>
            <li><NuxtLink to="/">Charitable actions</NuxtLink></li>
            <li><NuxtLink to="/">Environment</NuxtLink></li>
          </ul>
        </div>

        <div class="footer-col">
          <h3>Production</h3>
          <ul>
            <li><NuxtLink to="/">Technology</NuxtLink></li>
            <li><NuxtLink to="/">Products</NuxtLink></li>
            <li><NuxtLink to="/">Quality</NuxtLink></li>
            <li><NuxtLink to="/">Sales geography</NuxtLink></li>
            <li><NuxtLink to="/">Our customers</NuxtLink></li>
          </ul>
        </div>

        <div class="footer-col">
          <h3>Contact us</h3>
          <ul>
            <li><NuxtLink to="/">Addresses of factories</NuxtLink></li>
            <li><NuxtLink to="/">Dealers</NuxtLink></li>
            <li><NuxtLink to="/">Trading houses</NuxtLink></li>
            <li><NuxtLink to="/">Brand shops</NuxtLink></li>
          </ul>
        </div>

      </div>
    </div>
  </footer>
</template>

<script setup>
// Mengimpor ikon Lucide secara eksplisit
import { Facebook, Twitter, Youtube, Instagram } from 'lucide-vue-next';
</script>

<style scoped>
/* Reset dasar & Font */
.footer-section {
  padding: 80px 20px;
  font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
  color: #444;
  background-color: #fff;
  border-top: 1px solid #eee;
}

/* Container dengan max-width 1200px */
.container {
  max-width: 1200px;
  margin: 0 auto;
}

/* Grid System */
.footer-grid {
  display: grid;
  grid-template-columns: 1.5fr 1fr 1fr 1fr;
  gap: 50px;
}

/* Styling Kolom Umum */
.footer-col h3 {
  font-size: 1.15rem;
  color: #3f51b5; /* Warna biru sesuai gambar */
  margin-bottom: 25px;
  font-weight: 600;
  letter-spacing: 0.5px;
}

.footer-col ul {
  list-style: none;
  padding: 0;
  margin: 0;
}

.footer-col ul li {
  margin-bottom: 14px;
}

.footer-col ul li a {
  text-decoration: none;
  color: #666;
  font-size: 0.95rem;
  transition: color 0.2s ease-in-out;
}

.footer-col ul li a:hover {
  color: #3f51b5;
}

/* Branding Column Specifics */
.copyright-text {
  font-size: 1.1rem;
  font-weight: bold;
  color: #556ee6;
  line-height: 1.4;
  margin-bottom: 20px;
  text-transform: uppercase;
}

.theme-info {
  font-size: 0.85rem;
  color: #888;
  line-height: 1.6;
  margin-bottom: 25px;
}

.highlight {
  color: #a0a0c0;
}

/* Social Icons styling */
.social-icons {
  display: flex;
  gap: 20px;
  align-items: center;
}

.icon-link {
  text-decoration: none;
  color: #999;
  transition: color 0.2s ease-in-out, transform 0.2s ease-in-out;
  display: flex;
  align-items: center;
  justify-content: center;
}

.icon-link:hover {
  color: #3f51b5;
  transform: translateY(-2px); /* Efek hover halus */
}

/* Responsif untuk layar kecil */
@media (max-width: 992px) {
  .footer-grid {
    grid-template-columns: 1fr 1fr;
    gap: 40px;
  }
}

@media (max-width: 576px) {
  .footer-grid {
    grid-template-columns: 1fr;
    text-align: center;
  }
  
  .social-icons {
    justify-content: center;
  }
}
</style>