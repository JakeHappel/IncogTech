<template>
  <section id="services" class="section services">
    <div class="container">
      <h2 class="section-title">IT Support Plans</h2>
      <p class="lead">Choose a level that fits your business. All plans include proactive monitoring and remote support.</p>

      <div class="tiers">
        <article class="card tier">
          <h3>Basic</h3>
          <p class="price">$99 / mo</p>
          <ul>
            <li>Remote support (business hours)</li>
            <li>Monthly checkups</li>
            <li>Security patching</li>
          </ul>
          <button class="card-cta" @click="request('Basic')">Request Quote</button>
        </article>

        <article class="card tier featured">
          <h3>Standard</h3>
          <p class="price">$249 / mo</p>
          <ul>
            <li>24/7 remote support</li>
            <li>On-site visits (as needed)</li>
            <li>Priority response</li>
          </ul>
          <button class="card-cta" @click="request('Standard')">Request Quote</button>
        </article>

        <article class="card tier">
          <h3>Premium</h3>
          <p class="price">$499 / mo</p>
          <ul>
            <li>Dedicated engineer</li>
            <li>Network & infrastructure management</li>
            <li>Advanced security services</li>
          </ul>
          <button class="card-cta" @click="request('Premium')">Request Quote</button>
        </article>
      </div>
    </div>
  </section>
</template>

<script setup>
function request(plan) {
  const el = document.getElementById('request-quote')
  if (el) {
    el.scrollIntoView({ behavior: 'smooth', block: 'start' })
    // optional: pre-fill a hidden input or set a query param in the form
    const planInput = document.querySelector('input[name="preferredPlan"]')
    if (planInput) planInput.value = plan
  }
}
</script>

<style scoped>
.section { padding: 3.25rem 1rem; background: #fff; color: #222; }
.section-title { font-size: 1.5rem; margin-bottom: 0.25rem; }
.lead { color: #666; margin-bottom: 1.5rem; }

.tiers {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 1rem;
  align-items: stretch;
}
.card {
  border: 1px solid rgba(30,30,30,0.06);
  border-radius: 10px;
  padding: 1.25rem;
  background: #fafafa;
  display: flex;
  flex-direction: column;
  gap: 0.75rem;
}
.card h3 { margin: 0; }
.price { font-weight: 700; color: #2b2f34; font-size: 1.05rem; }
.card ul { margin: 0; padding-left: 1.1rem; color: #555; }
.card-cta {
  margin-top: auto;
  background: #2b2f34;
  color: #fff;
  border: none;
  padding: 8px 12px;
  border-radius: 8px;
  cursor: pointer;
}
.featured {
  transform: translateY(-6px);
  box-shadow: 0 8px 30px rgba(20,20,20,0.06);
}

/* Responsive */
@media (max-width: 1000px) {
  .tiers { grid-template-columns: repeat(1,1fr); }
}
</style>