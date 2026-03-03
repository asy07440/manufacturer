<script setup>
import { ref, onMounted, onUnmounted } from "vue";

const isMenuOpen = ref(false);

const toggleMenu = () => {
  isMenuOpen.value = !isMenuOpen.value;
  // Mencegah scroll pada body saat menu terbuka agar user tidak bingung
  if (process.client) {
    document.body.style.overflow = isMenuOpen.value ? "hidden" : "auto";
  }
};

const closeMenu = () => {
  isMenuOpen.value = false;
  if (process.client) {
    document.body.style.overflow = "auto";
  }
};

const navLinks = [
  { name: "Home", path: "/" },
  { name: "About Us", path: "/about" },
  { name: "Services", path: "/services" },
  { name: "Blog", path: "/blog" },
  { name: "Shop", path: "/shop" },
  { name: "Contacts", path: "/contacts" },
];

// Menutup menu jika layar di-resize ke desktop secara otomatis
const handleResize = () => {
  if (window.innerWidth > 992 && isMenuOpen.value) {
    closeMenu();
  }
};

onMounted(() => {
  window.addEventListener("resize", handleResize);
});

onUnmounted(() => {
  window.removeEventListener("resize", handleResize);
});
</script>

<template>
  <header class="header-wrapper">
    <div class="top-bar desktop-only">
      <div class="container flex-between">
        <div class="contact-info">
          <span>Office: <strong>123-456-789</strong></span>
          <span class="divider-v"></span>
          <span>Factory: <strong>123-456-789</strong></span>
        </div>
        <div class="top-bar-right">
          <div class="search-box">
            <input type="text" placeholder="Search..." />
            <svg
              class="icon-search"
              width="16"
              height="16"
              viewBox="0 0 24 24"
              fill="none"
              stroke="currentColor"
              stroke-width="2"
            >
              <circle cx="11" cy="11" r="8"></circle>
              <line x1="21" y1="21" x2="16.65" y2="16.65"></line>
            </svg>
          </div>
        </div>
      </div>
    </div>

    <nav class="main-nav">
      <div class="container flex-between">
        <div class="logo">
          <NuxtLink to="/">
            <span class="logo-accent">M</span>anufacturer
          </NuxtLink>
        </div>

        <ul class="nav-links desktop-only">
          <li v-for="link in navLinks" :key="link.path">
            <NuxtLink :to="link.path" active-class="active">{{
              link.name
            }}</NuxtLink>
          </li>
        </ul>

        <div class="nav-actions desktop-only">
          <button class="quote-btn">
            Get a Quote
            <span class="arrow">→</span>
          </button>
        </div>

        <button
          class="mobile-toggle"
          @click="toggleMenu"
          :class="{ 'is-active': isMenuOpen }"
          aria-label="Toggle Menu"
        >
          <span></span>
          <span></span>
          <span></span>
        </button>
      </div>
    </nav>

    <div class="drawer-wrapper">
      <Transition name="fade">
        <div v-if="isMenuOpen" class="drawer-overlay" @click="closeMenu"></div>
      </Transition>

      <Transition name="slide">
        <div v-if="isMenuOpen" class="drawer-content">
          <div class="drawer-header">
            <div class="logo">
              <span class="logo-accent">M</span>anufacturer
            </div>
            <button class="close-btn" @click="closeMenu">&times;</button>
          </div>

          <ul class="mobile-nav-links">
            <li v-for="link in navLinks" :key="link.path">
              <NuxtLink
                :to="link.path"
                @click="closeMenu"
                active-class="active"
              >
                {{ link.name }}
              </NuxtLink>
            </li>
          </ul>

          <div class="drawer-footer">
            <button class="quote-btn w-full">Get a Quote</button>
            <div class="mobile-contact">
              <p><strong>Office:</strong> 123-456-789</p>
              <p><strong>Factory:</strong> 123-456-789</p>
            </div>
          </div>
        </div>
      </Transition>
    </div>
  </header>
</template>

<style scoped>
/* --- KONFIGURASI WARNA & VARIABEL --- */
.header-wrapper {
  --primary: #5d75f5;
  --dark: #1e293b;
  --text: #475569;
  --border: #e2e8f0;
  --white: #ffffff;
  --transition: all 0.3s cubic-bezier(0.4, 0, 0.2, 1);
  width: 100%;
}

.container {
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 24px;
  width: 100%;
}

.flex-between {
  display: flex;
  justify-content: space-between;
  align-items: center;
}

/* --- TOP BAR --- */
.top-bar {
  background-color: #f8fafc;
  border-bottom: 1px solid var(--border);
  padding: 10px 0;
  font-size: 13px;
  color: var(--text);
}

.divider-v {
  width: 1px;
  height: 12px;
  background: #cbd5e1;
  display: inline-block;
  margin: 0 15px;
  vertical-align: middle;
}

.search-box {
  display: flex;
  align-items: center;
  background: var(--white);
  border: 1px solid var(--border);
  border-radius: 20px;
  padding: 5px 15px;
}

.search-box input {
  border: none;
  font-size: 13px;
  outline: none;
  width: 100px;
  transition: var(--transition);
}

.search-box input:focus {
  width: 160px;
}

/* --- MAIN NAV --- */
.main-nav {
  background: rgba(255, 255, 255, 0.9);
  backdrop-filter: blur(12px);
  padding: 15px 0;
  border-bottom: 1px solid var(--border);
  position: sticky;
  top: 0;
  z-index: 100;
}

.logo a {
  font-size: 24px;
  font-weight: 800;
  color: var(--dark);
  text-decoration: none;
  letter-spacing: -0.5px;
}

.logo-accent {
  color: var(--primary);
}

.nav-links {
  display: flex;
  list-style: none;
  gap: 30px;
}

.nav-links a {
  text-decoration: none;
  color: var(--text);
  font-weight: 600;
  font-size: 15px;
  transition: var(--transition);
}

.nav-links a:hover,
.nav-links a.active {
  color: var(--primary);
}

/* --- BUTTONS --- */
.quote-btn {
  background: var(--primary);
  color: var(--white);
  border: none;
  padding: 12px 22px;
  border-radius: 8px;
  font-weight: 600;
  display: flex;
  align-items: center;
  gap: 8px;
  cursor: pointer;
  transition: var(--transition);
}

.quote-btn:hover {
  background: #4a63e0;
  transform: translateY(-2px);
  box-shadow: 0 5px 15px rgba(93, 117, 245, 0.3);
}

.w-full {
  width: 100%;
  justify-content: center;
}

/* --- MOBILE TOGGLE --- */
.mobile-toggle {
  display: none;
  flex-direction: column;
  justify-content: center;
  gap: 5px;
  background: #f1f5f9;
  border: none;
  cursor: pointer;
  width: 40px;
  height: 40px;
  border-radius: 8px;
  padding: 10px;
  position: relative;
  z-index: 1100;
}

.mobile-toggle span {
  display: block;
  width: 20px;
  height: 2px;
  background: var(--dark);
  transition: var(--transition);
  margin: 0 auto;
}

/* --- DRAWER --- */
.drawer-overlay {
  position: fixed;
  inset: 0;
  background: rgba(15, 23, 42, 0.6);
  backdrop-filter: blur(4px);
  z-index: 1000;
}

.drawer-content {
  position: fixed;
  top: 0;
  right: 0;
  width: 85%;
  max-width: 320px;
  height: 100vh;
  background: var(--white);
  z-index: 1001;
  padding: 25px;
  display: flex;
  flex-direction: column;
  box-shadow: -5px 0 25px rgba(0, 0, 0, 0.15);
}

.drawer-header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 40px;
}

.close-btn {
  background: none;
  border: none;
  font-size: 32px;
  color: var(--text);
  cursor: pointer;
}

.mobile-nav-links {
  list-style: none;
  flex-grow: 1;
}

.mobile-nav-links li {
  margin-bottom: 10px;
}

.mobile-nav-links a {
  font-size: 18px;
  font-weight: 700;
  text-decoration: none;
  color: var(--dark);
  display: block;
  padding: 12px 15px;
  border-radius: 8px;
  transition: var(--transition);
}

.mobile-nav-links a.active {
  background: #f1f5f9;
  color: var(--primary);
}

.drawer-footer {
  border-top: 1px solid var(--border);
  padding-top: 25px;
}

.mobile-contact {
  margin-top: 20px;
  font-size: 14px;
  color: var(--text);
  line-height: 1.8;
}

/* --- RESPONSIVE LOGIC --- */
@media (max-width: 992px) {
  .desktop-only {
    display: none;
  }
  .mobile-toggle {
    display: flex;
  }
}

/* --- ANIMATIONS --- */
.slide-enter-active,
.slide-leave-active {
  transition: transform 0.4s cubic-bezier(0.16, 1, 0.3, 1);
}
.slide-enter-from,
.slide-leave-to {
  transform: translateX(100%);
}

.fade-enter-active,
.fade-leave-active {
  transition: opacity 0.3s ease;
}
.fade-enter-from,
.fade-leave-to {
  opacity: 0;
}

/* Hamburger Animation */
.mobile-toggle.is-active span:nth-child(1) {
  transform: translateY(7px) rotate(45deg);
}
.mobile-toggle.is-active span:nth-child(2) {
  opacity: 0;
}
.mobile-toggle.is-active span:nth-child(3) {
  transform: translateY(-7px) rotate(-45deg);
}
</style>
