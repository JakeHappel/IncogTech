<template>
  <section id="home" class="hero" :style="heroStyle" aria-label="Intro">
    <div class="hero-overlay">
      <div class="container hero-content">
        <h1>Security-focused solutions for residential and small business</h1>
        <p class="subtitle">Managed IT services, Security solutions, access control, network installs — designed for modern homes and businesses.</p>
        <div class="cta-row">
          <button class="primary" @click="scrollTo('#services')">See Support Plans</button>
          <button class="ghost" @click="$emit('go-quote')" @click.native="goQuote">Request a Quote</button>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
import { computed } from 'vue'

/*
  You can replace the background by setting a CSS variable --hero-bg in global stylesheet or
  add inline style here. For now this component exposes a placeholder background with a soft gradient.
*/
const heroStyle = computed(() => ({
  // Example: replace with `backgroundImage: 'url(/assets/your-image.jpg)'
  backgroundImage: 'url(public/3306588.jpg)',
  backgroundSize: 'cover',
  backgroundPosition: 'center center',
}))
function goQuote() {
  const el = document.getElementById('request-quote')
  if (el) el.scrollIntoView({ behavior: 'smooth', block: 'start' })
}
</script>

<style scoped>
.hero {
  min-height: 100vh;
  display: flex;
  align-items: center;
  position: relative;
  color: #1f1f1f;
}
.hero-overlay {
  width: 100%;
  background: linear-gradient(to bottom, rgba(255,255,255,0.0) 0%, rgba(255,255,255,0.85) 65%);
}
.hero-content {
  padding: 4rem 1rem;
  max-width: 1100px;
  margin: 0 auto;
  text-align: left;
}
.subtitle {
  margin-top: 0.5rem;
  color: #595959;
  max-width: 720px;
}
.cta-row {
  margin-top: 1.25rem;
  display: flex;
  gap: 0.75rem;
  align-items: center;
}
.primary {
  background: #2b2f34;
  color: #fff;
  border: none;
  padding: 10px 16px;
  border-radius: 8px;
  cursor: pointer;
}
.ghost {
  background: transparent;
  border: 1px solid rgba(40,40,40,0.12);
  padding: 9px 14px;
  border-radius: 8px;
  cursor: pointer;
}
@media (max-width: 720px) {
  .hero-content { padding: 3rem 1rem;}
  .cta-row { flex-direction: column; align-items: stretch; }
}
</style>