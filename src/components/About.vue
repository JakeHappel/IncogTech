<template>
  <section id="about" class="section">
    <div class="container about-grid">
      <div class="about-text">
        <h2>About Us</h2>
        <p>We deliver dependable IT solutions with a neutral, business-first approach. Our team focuses on reducing downtime, securing your assets, and providing clear, actionable advice.</p>
        <ul>
          <li>Trusted for small & medium businesses</li>
          <li>Security-first engineering practices</li>
          <li>Transparent pricing and SLAs</li>
        </ul>
      </div>
      <div class="about-image" aria-hidden="true">
        <!-- placeholder for image -->
        <div class="img-placeholder">Team / Office Image</div>
      </div>
    </div>
  </section>
</template>

<script setup>
</script>

<style scoped>
.about-grid {
  display: grid;
  grid-template-columns: 1fr 420px;
  gap: 1.25rem;
  align-items: center;
}
.about-text p { color: #555; }
.img-placeholder {
  height: 220px;
  background: linear-gradient(180deg,#f6f6f7,#efeff0);
  border-radius: 8px;
  border: 1px dashed rgba(30,30,30,0.06);
  display: flex;
  align-items: center;
  justify-content: center;
  color: #777;
}
@media (max-width: 900px) {
  .about-grid { grid-template-columns: 1fr; }
  .img-placeholder { height: 180px; }
}
</style>