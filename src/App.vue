<template>
  <div id="app">
    <header>
      <nav>
        <ul>
          <li><a href="#home" @click="scrollTo('home')">Home</a></li>
          <li><a href="#services" @click="scrollTo('services')">Services</a></li>
          <li><a href="#about" @click="scrollTo('about')">About</a></li>
          <li><a href="#contact" @click="scrollTo('contact')">Contact</a></li>
        </ul>
      </nav>
    </header>

    <section id="home" class="hero">
      <div class="container">
        <Transition name="fade">
          <h1 v-if="showHero">Secure Your Digital World</h1>
        </Transition>
        <p>Expert IT Security, Networking, and Support for Residential Homes and Small Businesses</p>
        <a href="#contact" class="btn" @click="scrollTo('contact')">Get Started</a>
      </div>
    </section>

    <section id="services">
      <div class="container">
        <h2>Our Services</h2>
        <div class="services-grid">
          <div class="service-card">
            <h3>Network Setup & Optimization</h3>
            <p>Professional installation and optimization of home and office networks for seamless connectivity.</p>
          </div>
          <div class="service-card">
            <h3>Cybersecurity Solutions</h3>
            <p>Protect your data with firewalls, antivirus, and threat monitoring tailored for small setups.</p>
          </div>
          <div class="service-card">
            <h3>IT Support & Maintenance</h3>
            <p>Reliable on-site and remote support to keep your systems running smoothly without downtime.</p>
          </div>
        </div>
      </div>
    </section>

    <section id="about">
      <div class="container">
        <h2>About SecureNet Solutions</h2>
        <p>With over 10 years of experience, we specialize in making advanced IT security and networking accessible and affordable for residential customers and small businesses. Our team ensures your online presence is safe, fast, and efficient.</p>
      </div>
    </section>

    <section id="contact">
      <div class="container">
        <h2>Contact Us</h2>
        <form @submit.prevent="submitForm">
          <input v-model="form.name" placeholder="Your Name" required>
          <input v-model="form.email" type="email" placeholder="Your Email" required>
          <textarea v-model="form.message" placeholder="Your Message" rows="5" required></textarea>
          <button type="submit" class="btn">Send Message</button>
        </form>
        <p>Email: info@securenetsolutions.com | Phone: (555) 123-4567</p>
      </div>
    </section>

    <footer>
      <div class="container">
        <p>&copy; 2025 SecureNet Solutions. All rights reserved.</p>
      </div>
    </footer>
  </div>
</template>

<script>
export default {
  name: 'App',
  data() {
    return {
      showHero: true,
      form: {
        name: '',
        email: '',
        message: ''
      }
    };
  },
  methods: {
    scrollTo(section) {
      document.getElementById(section).scrollIntoView({ behavior: 'smooth' });
    },
    submitForm() {
      alert('Thank you for your message! We\'ll get back to you soon.');
      this.form = { name: '', email: '', message: '' };
    }
  },
  mounted() {
    setTimeout(() => { this.showHero = false; }, 2000);
    setTimeout(() => { this.showHero = true; }, 3000);
  }
};
</script>

<style scoped>
* { margin: 0; padding: 0; box-sizing: border-box; }
body { font-family: Arial, sans-serif; line-height: 1.6; color: #333; }
.container { max-width: 1200px; margin: 0 auto; padding: 0 20px; }
header { background: #1a1a1a; color: white; padding: 1rem 0; position: fixed; width: 100%; top: 0; z-index: 1000; }
nav ul { list-style: none; display: flex; justify-content: center; }
nav li { margin: 0 1rem; }
nav a { color: white; text-decoration: none; }
.hero { background: linear-gradient(to right, #007bff, #0056b3); color: white; text-align: center; padding: 150px 0 100px; }
.hero h1 { font-size: 3rem; margin-bottom: 1rem; }
.hero p { font-size: 1.2rem; margin-bottom: 2rem; }
.btn { background: #ff6b35; color: white; padding: 10px 20px; text-decoration: none; border-radius: 5px; display: inline-block; border: none; cursor: pointer; }
section { padding: 80px 0; }
#services { background: #f8f9fa; }
.services-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(300px, 1fr)); gap: 2rem; }
.service-card { background: white; padding: 2rem; border-radius: 8px; box-shadow: 0 2px 10px rgba(0,0,0,0.1); text-align: center; }
.service-card h3 { margin-bottom: 1rem; color: #007bff; }
#about { text-align: center; }
#about h2, #contact h2, #services h2 { text-align: center; margin-bottom: 2rem; font-size: 2.5rem; }
#about p { font-size: 1.1rem; max-width: 800px; margin: 0 auto; }
#contact { background: #1a1a1a; color: white; text-align: center; }
form { max-width: 600px; margin: 0 auto; display: flex; flex-direction: column; gap: 1rem; }
input, textarea { padding: 10px; border: none; border-radius: 5px; }
footer { background: #333; color: white; text-align: center; padding: 1rem 0; }
#contact p { margin-top: 1rem; }
.fade-enter-active, .fade-leave-active { transition: opacity 0.5s; }
.fade-enter-from, .fade-leave-to { opacity: 0; }
</style>