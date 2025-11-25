<template>
  <section id="home" class="hero" aria-label="Intro">
    <div class="hero-overlay">
      <div class="container hero-content">
        <h1>Reliable, neutral, and secure IT services</h1>
        <p class="subtitle">Managed IT support, access control, network installs, and security — designed for modern businesses.</p>
        <div class="cta-row">
          <button class="primary" @click="scrollTo('#services')">See Support Plans</button>
          <button class="ghost" @click="goQuote">Request a Quote</button>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
/* No background logic here — the site background is provided by CSS (fixed layer).
   Keep the hero as a transparent/content container that sits above the fixed background. */

function scrollTo(hash) {
  const el = document.querySelector(hash)
  if (el) el.scrollIntoView({ behavior: 'smooth', block: 'start' })
}
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
  /* transparent so the fixed background shows through */
  background: transparent;
}

/* Overlay keeps text readable while still revealing the background */
.hero-overlay {
  width: 100%;
  /* slightly more translucent than before so the fixed image shows through */
  background: linear-gradient(to bottom, rgba(255,255,255,0.02) 0%, rgba(255,255,255,0.72) 70%);
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
  .hero-content { padding: 3rem 1rem; }
  .cta-row { flex-direction: column; align-items: stretch; }
}
</style>