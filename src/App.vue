<script setup>
import Navigation from './components/Navigation.vue'
import Hero from './components/Hero.vue'
import About from './components/About.vue'
import Services from './components/Services.vue'
import Contact from './components/Contact.vue'
import Footer from './components/Footer.vue'
</script>

<template>
  <div id="app">
    <Navigation />
    <Hero />
    <About />
    <Services />
    <Contact />
    <Footer />
  </div>
</template>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

body {
  font-family: 'Arial', sans-serif;
  line-height: 1.6;
  color: #333;
}

#app {
  width: 100%;
  overflow-x: hidden;
}

.container {
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 20px;
}

.section {
  padding: 80px 0;
}

.section-title {
  font-size: 2.5rem;
  text-align: center;
  margin-bottom: 3rem;
  color: #2c3e50;
}

.btn {
  display: inline-block;
  padding: 12px 30px;
  background: #6a4c93;
  color: white;
  text-decoration: none;
  border-radius: 30px;
  transition: all 0.3s ease;
  border: none;
  cursor: pointer;
  font-size: 1rem;
}

.btn:hover {
  background: #553a7a;
  transform: translateY(-2px);
}

.btn-secondary {
  background: transparent;
  color: #6a4c93;
  border: 2px solid #6a4c93;
}

.btn-secondary:hover {
  background: #6a4c93;
  color: white;
}
</style>
