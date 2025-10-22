<template>
  <header class="nav-wrap">
    <div class="container nav-inner">
      <div class="brand">
        <!-- Replace the text with an <img> when you have a logo -->
        <div class="logo-placeholder" aria-hidden="true">LOGO</div>
      </div>

      <nav :class="['main-nav', { open: mobileOpen }]" aria-label="Primary">
        <a href="#home" @click.prevent="scrollTo('#home')">Home</a>
        <a href="#services" @click.prevent="scrollTo('#services')">IT Support</a>
        <a href="#other-services" @click.prevent="scrollTo('#other-services')">Other Services</a>
        <a href="#about" @click.prevent="scrollTo('#about')">About</a>
      </nav>

      <div class="nav-actions">
        <button class="quote-cta" @click="$emit('go-quote')" aria-label="Request a Quote">
          Request a Quote
        </button>

        <button class="mobile-toggle" @click="mobileOpen = !mobileOpen" :aria-expanded="mobileOpen" aria-label="Toggle menu">
          <span class="hamburger"></span>
        </button>
      </div>
    </div>
  </header>
</template>

<script setup>
import { ref } from 'vue'

const mobileOpen = ref(false)

function scrollTo(hash) {
  mobileOpen.value = false
  const el = document.querySelector(hash)
  if (el) el.scrollIntoView({ behavior: 'smooth', block: 'start' })
}
</script>

<style scoped>
.nav-wrap {
  position: sticky;
  top: 0;
  z-index: 60;
  backdrop-filter: blur(4px);
  background: rgba(250,250,250,0.75);
  border-bottom: 1px solid rgba(0,0,0,0.05);
}
.nav-inner {
  display: flex;
  align-items: center;
  gap: 1rem;
  padding: 0.6rem 1rem;
}
.brand {
  flex: 0 0 auto;
}
.logo-placeholder {
  font-weight: 700;
  color: #343434;
  background: #f2f2f2;
  border-radius: 6px;
  padding: 8px 12px;
  letter-spacing: 1px;
}
.main-nav {
  display: flex;
  gap: 1rem;
  margin-left: 1.5rem;
  align-items: center;
  flex: 1 1 auto;
}
.main-nav a {
  color: #444;
  text-decoration: none;
  padding: 8px 10px;
  border-radius: 6px;
}
.main-nav a:hover {
  background: rgba(0,0,0,0.04);
}
.nav-actions {
  display: flex;
  gap: 0.75rem;
  align-items: center;
  flex: 0 0 auto;
}
.quote-cta {
  background: #2b2f34;
  color: #fff;
  border: none;
  padding: 8px 14px;
  border-radius: 6px;
  cursor: pointer;
}
.quote-cta:hover { opacity: 0.95; }
.mobile-toggle {
  display: none;
  background: transparent;
  border: none;
  padding: 6px;
}
.hamburger {
  width: 20px;
  height: 2px;
  background: #222;
  display: block;
  position: relative;
}
.hamburger::after, .hamburger::before {
  content: '';
  position: absolute;
  left: 0;
  right: 0;
  height: 2px;
  background: #222;
}
.hamburger::before { top: -6px; }
.hamburger::after { top: 6px; }

/* Responsive */
@media (max-width: 900px) {
  .main-nav { 
    position: absolute;
    right: 1rem;
    top: 64px;
    background: rgba(255,255,255,0.98);
    flex-direction: column;
    padding: 12px;
    border-radius: 8px;
    box-shadow: 0 6px 20px rgba(20,20,20,0.06);
    display: none;
    min-width: 200px;
  }
  .main-nav.open { display: flex; }
  .mobile-toggle { display: inline-block; }
  .nav-inner { gap: 0.5rem; }
}
</style>