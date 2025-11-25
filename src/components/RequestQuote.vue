<template>
  <section id="request-quote" class="section quote-section" aria-label="Request a quote">
    <div class="container">
      <h2>Request a Quote</h2>
      <p class="lead">Tell us a bit about your needs and we'll get back to you within one business day.</p>
      
      <form class="quote-form" action="https://formsubmit.co/Jake@IncogTech.com" method="POST" @submit.prevent="submit">
        <div class="form-grid">
          <label>
            Full name
            <input required type="text" name="name" v-model="form.name" placeholder="Jane Doe" />
          </label>

          <label>
            Business email
            <input required type="email" name="email" v-model="form.email" placeholder="name@company.com" />
          </label>

          <label>
            Company
            <input type="text" name="company" v-model="form.company" placeholder="Company name (optional)" />
          </label>

          <label>
            Phone
            <input type="tel" name="phone" v-model="form.phone" placeholder="(optional)" />
          </label>
        </div>

        <label class="full">
          Preferred plan (optional)
          <input type="text" name="preferredPlan" v-model="form.plan" placeholder="Basic / Standard / Premium" />
        </label>

        <label class="full">
          Project details
          <textarea required name="details" v-model="form.details" rows="5" placeholder="Describe the work you need..."></textarea>
        </label>

        <div class="form-actions">
          <button type="submit" class="primary">Send Request</button>
          <button type="button" class="ghost" @click="clear">Clear</button>
        </div>

        <p v-if="sent" class="notice">Thanks — your request has been recorded locally. Integrate a backend or email action to complete submission.</p>
      </form>
    </div>
  </section>
</template>

<script setup>
import { reactive, ref } from 'vue'
const form = reactive({
  name: '',
  email: '',
  company: '',
  phone: '',
  plan: '',
  details: '',
})
const sent = ref(false)

function submit() {
  // This is a placeholder. Hook this up to an API endpoint, serverless function, or email provider.
  console.log('Quote request:', JSON.parse(JSON.stringify(form)))
  sent.value = true
  setTimeout(() => (sent.value = false), 6000)
  clear(false)
}

function clear(reset = true) {
  if (!reset) {
    form.name = ''
    form.email = ''
    form.company = ''
    form.phone = ''
    form.plan = ''
    form.details = ''
  } else {
    form.name = ''
    form.email = ''
    form.company = ''
    form.phone = ''
    form.plan = ''
    form.details = ''
  }
}
</script>

<style scoped>

#request-quote{
  padding:2.5rem
}
.quote-section { background: #fff; padding-bottom: 3rem; }
.quote-form { margin-top: 1rem; display: block; }
.form-grid {
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  gap: 0.8rem;
}
label {
  display: flex;
  flex-direction: column;
  font-size: 0.95rem;
  color: #333;
}
input, textarea {
  margin-top: 0.5rem;
  padding: 8px 10px;
  border-radius: 8px;
  border: 1px solid rgba(30,30,30,0.08);
  background: #fff;
  outline: none;
}
.full { margin-top: 0.8rem; }
.form-actions {
  margin-top: 1rem;
  display: flex;
  gap: 0.6rem;
}
.notice {
  margin-top: 0.8rem;
  color: #2b7a2b;
  font-weight: 600;
}
@media (max-width: 900px) {
  .form-grid { grid-template-columns: 1fr; }
}
</style>