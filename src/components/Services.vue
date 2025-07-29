<template>
  <section id="services" class="section services">
    <div class="container">
      <h2 class="section-title">Our Services</h2>
      <p class="services-intro">
        We offer a range of evidence-based therapeutic services designed to support 
        your healing journey and promote lasting wellness.
      </p>
      
      <div class="services-grid">
        <div class="service-card" v-for="service in services" :key="service.id">
          <div class="service-icon">
            <span v-html="service.icon"></span>
          </div>
          <div class="service-content">
            <span class="service-number">{{ service.number }}</span>
            <h3>{{ service.title }}</h3>
            <p>{{ service.description }}</p>
            <ul class="service-features" v-if="service.features">
              <li v-for="feature in service.features" :key="feature">{{ feature }}</li>
            </ul>
            <div class="service-footer">
              <span class="service-duration">{{ service.duration }}</span>
              <a href="#contact" class="btn btn-secondary" @click="scrollTo('contact')">
                Learn More
              </a>
            </div>
          </div>
        </div>
      </div>

      <div class="additional-info">
        <div class="info-card">
          <h3>Insurance & Payment</h3>
          <p>We accept most major insurance plans and offer flexible payment options. 
             Please contact us to verify your coverage and discuss payment arrangements.</p>
        </div>
        <div class="info-card">
          <h3>Session Format</h3>
          <p>We offer both in-person and virtual therapy sessions to accommodate your 
             needs and preferences. All sessions are confidential and conducted in a 
             safe, supportive environment.</p>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
import { ref } from 'vue'

const services = ref([
  {
    id: 1,
    number: '01.',
    title: 'Individual Trauma Therapy',
    icon: '🧠',
    description: 'One-on-one sessions that provide a personalized approach to healing from past trauma and building resilience. Evidence-based modalities are used to support emotional well-being and recovery.',
    features: [
      'Trauma-focused cognitive therapy',
      'EMDR (Eye Movement Desensitization)',
      'Somatic therapy techniques',
      'Mindfulness-based interventions'
    ],
    duration: '50-60 minutes'
  },
  {
    id: 2,
    number: '02.',
    title: 'Accelerated Resolution Therapy',
    icon: '⚡',
    description: 'Accelerated Resolution Therapy (ART) uses bilateral eye movements and does not require clients to speak in detail about their traumatic incident.',
    features: [
      'Rapid trauma processing',
      'No detailed trauma discussion required',
      'Bilateral stimulation techniques',
      'Memory reconsolidation therapy'
    ],
    duration: '60-90 minutes'
  },
  {
    id: 3,
    number: '03.',
    title: 'Mental Wellness Presentations',
    icon: '🌱',
    description: 'Presentations focused on mental wellness, nervous-system regulation and other basic wellness principles from an evidence-based perspective tailored to your needs.',
    features: [
      'Workplace wellness programs',
      'Community education sessions',
      'Stress management workshops',
      'Mental health awareness training'
    ],
    duration: '1-2 hours'
  },
  {
    id: 4,
    number: '04.',
    title: 'Anxiety & Depression Support',
    icon: '🌈',
    description: 'Comprehensive support for managing anxiety and depression through therapeutic interventions, coping strategies, and wellness planning.',
    features: [
      'Cognitive behavioral therapy',
      'Anxiety management techniques',
      'Depression treatment protocols',
      'Relapse prevention planning'
    ],
    duration: '50 minutes'
  }
])

const scrollTo = (elementId) => {
  const element = document.getElementById(elementId)
  if (element) {
    element.scrollIntoView({ behavior: 'smooth' })
  }
}
</script>

<style scoped>
.services {
  background: #f8f9fa;
}

.services-intro {
  text-align: center;
  font-size: 1.2rem;
  color: #666;
  max-width: 600px;
  margin: 0 auto 3rem;
  line-height: 1.6;
}

.services-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
  gap: 2rem;
  margin-bottom: 4rem;
}

.service-card {
  background: white;
  border-radius: 20px;
  padding: 2rem;
  box-shadow: 0 10px 30px rgba(0, 0, 0, 0.1);
  transition: transform 0.3s ease, box-shadow 0.3s ease;
  position: relative;
  overflow: hidden;
}

.service-card::before {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  height: 4px;
  background: linear-gradient(90deg, #4d5d44, #3a4633);
}

.service-card:hover {
  transform: translateY(-5px);
  box-shadow: 0 20px 40px rgba(0, 0, 0, 0.15);
}

.service-icon {
  font-size: 3rem;
  margin-bottom: 1rem;
}

.service-number {
  color: #4d5d44;
  font-weight: bold;
  font-size: 1.2rem;
}

.service-content h3 {
  color: #2c3e50;
  font-size: 1.5rem;
  margin: 1rem 0;
}

.service-content p {
  color: #666;
  line-height: 1.6;
  margin-bottom: 1.5rem;
}

.service-features {
  list-style: none;
  padding: 0;
  margin-bottom: 2rem;
}

.service-features li {
  padding: 0.5rem 0;
  color: #555;
  position: relative;
  padding-left: 1.5rem;
}

.service-features li::before {
  content: '✓';
  position: absolute;
  left: 0;
  color: #4d5d44;
  font-weight: bold;
}

.service-footer {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding-top: 1rem;
  border-top: 1px solid #eee;
}

.service-duration {
  color: #888;
  font-size: 0.9rem;
  font-style: italic;
}

.additional-info {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
  gap: 2rem;
}

.info-card {
  background: white;
  border-radius: 15px;
  padding: 2rem;
  text-align: center;
  box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
}

.info-card h3 {
  color: #4d5d44;
  margin-bottom: 1rem;
}

.info-card p {
  color: #666;
  line-height: 1.6;
}

@media (max-width: 768px) {
  .services-grid {
    grid-template-columns: 1fr;
  }

  .service-card {
    padding: 1.5rem;
  }

  .service-footer {
    flex-direction: column;
    gap: 1rem;
    align-items: stretch;
  }

  .additional-info {
    grid-template-columns: 1fr;
  }
}
</style>
