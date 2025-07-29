<template>
  <header class="navbar">
    <div class="container">
      <div class="nav-content">
        <div class="logo">
          <h2>AFLC Services</h2>
          <p class="tagline">Compassionate Counselling Services</p>
        </div>
        <nav class="nav-menu" :class="{ active: isMenuOpen }">
          <a href="#home" @click="scrollTo('home')">Home</a>
          <a href="#about" @click="scrollTo('about')">About</a>
          <a href="#services" @click="scrollTo('services')">Services</a>
          <a href="#contact" @click="scrollTo('contact')">Contact</a>
          <a href="#" class="btn btn-primary">Book Appointment</a>
        </nav>
        <div class="mobile-menu-btn" @click="toggleMenu">
          <span></span>
          <span></span>
          <span></span>
        </div>
      </div>
    </div>
  </header>
</template>

<script setup>
import { ref } from 'vue'

const isMenuOpen = ref(false)

const toggleMenu = () => {
  isMenuOpen.value = !isMenuOpen.value
}

const scrollTo = (elementId) => {
  const element = document.getElementById(elementId)
  if (element) {
    element.scrollIntoView({ behavior: 'smooth' })
  }
  isMenuOpen.value = false
}
</script>

<style scoped>
.navbar {
  background: rgba(255, 255, 255, 0.95);
  backdrop-filter: blur(10px);
  position: fixed;
  top: 0;
  width: 100%;
  z-index: 1000;
  padding: 1rem 0;
  box-shadow: 0 2px 20px rgba(0, 0, 0, 0.1);
}

.nav-content {
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.logo h2 {
  color: #6a4c93;
  font-size: 1.8rem;
  margin-bottom: 0.2rem;
}

.tagline {
  font-size: 0.9rem;
  color: #666;
  font-style: italic;
}

.nav-menu {
  display: flex;
  align-items: center;
  gap: 2rem;
}

.nav-menu a {
  text-decoration: none;
  color: #333;
  font-weight: 500;
  transition: color 0.3s ease;
  position: relative;
}

.nav-menu a:not(.btn):hover {
  color: #6a4c93;
}

.nav-menu a:not(.btn)::after {
  content: '';
  position: absolute;
  width: 0;
  height: 2px;
  bottom: -5px;
  left: 0;
  background: #6a4c93;
  transition: width 0.3s ease;
}

.nav-menu a:not(.btn):hover::after {
  width: 100%;
}

.mobile-menu-btn {
  display: none;
  flex-direction: column;
  cursor: pointer;
  gap: 4px;
}

.mobile-menu-btn span {
  width: 25px;
  height: 3px;
  background: #333;
  transition: all 0.3s ease;
}

@media (max-width: 768px) {
  .nav-menu {
    position: fixed;
    top: 100%;
    left: 0;
    width: 100%;
    background: white;
    flex-direction: column;
    padding: 2rem;
    box-shadow: 0 10px 30px rgba(0, 0, 0, 0.1);
    transform: translateY(-100%);
    opacity: 0;
    visibility: hidden;
    transition: all 0.3s ease;
  }

  .nav-menu.active {
    transform: translateY(0);
    opacity: 1;
    visibility: visible;
  }

  .mobile-menu-btn {
    display: flex;
  }

  .logo h2 {
    font-size: 1.4rem;
  }

  .tagline {
    font-size: 0.8rem;
  }
}
</style>
