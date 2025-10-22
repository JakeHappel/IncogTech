<template>
  <div id="app">
    <NavBar @go-quote="scrollToQuote" />
    <main>
      <Hero />
      <Services />
      <OtherServices />
      <About />
      <RequestQuote ref="quoteSection" />
    </main>
    <footer class="site-footer">
      <div class="container">
        <p>© {{ new Date().getFullYear() }} IncogTech. All rights reserved.</p>
      </div>
    </footer>
  </div>
</template>

<script setup>
import { ref } from 'vue'
import NavBar from './components/NavBar.vue'
import Hero from './components/Hero.vue'
import Services from './components/Services.vue'
import OtherServices from './components/OtherServices.vue'
import About from './components/About.vue'
import RequestQuote from './components/RequestQuote.vue'

const quoteSection = ref(null)

function scrollToQuote() {
  // call the RequestQuote component's DOM element to scroll into view
  if (quoteSection.value && quoteSection.value.$el) {
    quoteSection.value.$el.scrollIntoView({ behavior: 'smooth', block: 'start' })
  } else {
    // fallback to anchor id
    const el = document.getElementById('request-quote')
    if (el) el.scrollIntoView({ behavior: 'smooth', block: 'start' })
  }
}
</script>