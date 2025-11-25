<template>
  <section id="other-services" class="section alt-bg">
    <div class="container">
      <h2 class="section-title">Our Services</h2>
      <p class="lead">Expertise to round out your infrastructure</p>

      <div class="grid services-grid">
        <article class="service-card">
          <h4>Security Solutions</h4>
          <p>Card readers, multi-factor entry systems, CCTV integration, and managed access policies.</p>
        </article>

        <article class="service-card">
          <h4>Network Architecture</h4>
          <p>Design and implementation of wired & wireless networks, switches, VLANs, and performance tuning.</p>
        </article>

        <article class="service-card">
          <h4>IT Installations</h4>
          <p>New office setups, workstation imaging, printer & peripheral installs, and migrations.</p>
        </article>

        <article class="service-card">
          <h4>Security Assessments</h4>
          <p>Vulnerability scanning, configuration reviews and actionable remediation plans.</p>
        </article>
      </div>
    </div>
  </section>
</template>

<script setup>
</script>

<style scoped>

#other-services {
  padding: 3rem;
}
.alt-bg { background: #fbfbfc; }
.services-grid {
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  gap: 1rem;
}
.service-card {
  background: #fff;
  border: 1px solid rgba(20,20,20,0.04);
  padding: 1rem;
  border-radius: 8px;
  color: #333;
}
@media (max-width: 900px) {
  .services-grid { grid-template-columns: 1fr; }
}
</style>