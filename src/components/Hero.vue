<template>
  <section id="home" class="hero">
    <div class="hero-content">
      <div class="hero-text">
        <h1 class="hero-title">
          Find Your Path to<br />
          <span class="highlight">Healing & Wellness</span>
        </h1>
        <p class="hero-subtitle">
          Providing trauma-informed and compassionate counselling services in a
          safe, supportive environment where you can begin your journey toward
          healing and inner peace.
        </p>
        <div class="hero-quote">
          <p>"We are all just walking each other home." - Ram Dass</p>
        </div>
        <div class="hero-buttons">
          <a
            href="#contact"
            class="btn btn-primary"
            @click="scrollTo('contact')"
          >
            Book a Session
          </a>
          <a
            href="#services"
            class="btn btn-secondary"
            @click="scrollTo('services')"
          >
            Learn More
          </a>
        </div>
      </div>
      <div class="hero-image">
        <div class="image-placeholder">
          <div class="peaceful-icon">🌿</div>
          <p>Professional Counselling Services</p>
        </div>
      </div>
    </div>
    <div class="hero-wave">
      <svg viewBox="0 0 1200 120" preserveAspectRatio="none">
        <path
          d="M0,0V60c100,40 200,40 300,20S500,40 600,60s200,20 300,20S1100,60 1200,40V0Z"
          fill="#f8f9fa"
        ></path>
      </svg>
    </div>
  </section>
</template>

<script setup>
const scrollTo = (elementId) => {
  const element = document.getElementById(elementId);
  if (element) {
    element.scrollIntoView({ behavior: "smooth" });
  }
};
</script>

<style scoped>
.hero {
  min-height: 100vh;
  background: linear-gradient(135deg, #cec390 0%, #4d5d44 100%);
  display: flex;
  align-items: center;
  position: relative;
  overflow: hidden;
  color: white;
  padding-top: 100px;
}

.hero::before {
  content: "";
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background: url('data:image/svg+xml,<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 100 100"><defs><pattern id="grain" width="100" height="100" patternUnits="userSpaceOnUse"><circle cx="50" cy="50" r="0.5" fill="rgba(255,255,255,0.1)"/></pattern></defs><rect width="100" height="100" fill="url(%23grain)"/></svg>');
  opacity: 0.1;
}

.hero-content {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 4rem;
  align-items: center;
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 2rem;
  position: relative;
  z-index: 2;
}

.hero-title {
  font-size: 3.5rem;
  font-weight: 700;
  line-height: 1.2;
  margin-bottom: 1.5rem;
}

.highlight {
  color: #4d5d44;
  position: relative;
}

.hero-subtitle {
  font-size: 1.2rem;
  line-height: 1.8;
  margin-bottom: 2rem;
  opacity: 0.9;
}

.hero-quote {
  background: rgba(255, 255, 255, 0.1);
  padding: 1.5rem;
  border-radius: 15px;
  margin: 2rem 0;
  border-left: 4px solid #cec390;
}

.hero-quote p {
  font-style: italic;
  font-size: 1.1rem;
  text-align: center;
}

.hero-buttons {
  display: flex;
  gap: 1rem;
  margin-top: 2rem;
}

.hero-image {
  display: flex;
  justify-content: center;
  align-items: center;
}

.image-placeholder {
  background: rgba(255, 255, 255, 0.1);
  backdrop-filter: blur(10px);
  border-radius: 20px;
  padding: 3rem;
  text-align: center;
  border: 2px solid rgba(255, 255, 255, 0.2);
}

.peaceful-icon {
  font-size: 4rem;
  margin-bottom: 1rem;
}

.hero-wave {
  position: absolute;
  bottom: 0;
  left: 0;
  width: 100%;
  overflow: hidden;
  line-height: 0;
}

.hero-wave svg {
  position: relative;
  display: block;
  width: calc(100% + 1.3px);
  height: 60px;
}

@media (max-width: 768px) {
  .hero-content {
    grid-template-columns: 1fr;
    gap: 2rem;
    text-align: center;
  }

  .hero-title {
    font-size: 2.5rem;
  }

  .hero-subtitle {
    font-size: 1.1rem;
  }

  .hero-buttons {
    justify-content: center;
    flex-direction: column;
    align-items: center;
  }

  .btn {
    width: 200px;
  }
}
</style>
