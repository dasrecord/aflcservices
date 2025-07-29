<template>
  <footer class="footer">
    <div class="container">
      <div class="footer-content">
        <div class="footer-section">
          <div class="footer-logo">
            <h3>AFLC Services</h3>
            <p class="footer-tagline">Compassionate Counselling Services</p>
          </div>
          <p class="footer-description">
            Providing trauma-informed and compassionate counselling services in
            a safe, supportive environment where healing begins.
          </p>
          <div class="footer-quote">
            <p>"We are all just walking each other home." - Ram Dass</p>
          </div>
        </div>

        <div class="footer-section">
          <h4>Quick Links</h4>
          <ul class="footer-links">
            <li><a href="#home" @click="scrollTo('home')">Home</a></li>
            <li><a href="#about" @click="scrollTo('about')">About</a></li>
            <li>
              <a href="#services" @click="scrollTo('services')">Services</a>
            </li>
            <li><a href="#contact" @click="scrollTo('contact')">Contact</a></li>
            <li><a href="#">Privacy Policy</a></li>
            <li><a href="#">Terms of Service</a></li>
          </ul>
        </div>

        <div class="footer-section">
          <h4>Services</h4>
          <ul class="footer-links">
            <li>
              <a href="#services" @click="scrollTo('services')"
                >Individual Therapy</a
              >
            </li>
            <li>
              <a href="#services" @click="scrollTo('services')"
                >Trauma Therapy</a
              >
            </li>
            <li>
              <a href="#services" @click="scrollTo('services')">ART Therapy</a>
            </li>
            <li>
              <a href="#services" @click="scrollTo('services')"
                >Wellness Presentations</a
              >
            </li>
            <li>
              <a href="#services" @click="scrollTo('services')"
                >Anxiety Support</a
              >
            </li>
            <li>
              <a href="#services" @click="scrollTo('services')"
                >Depression Support</a
              >
            </li>
          </ul>
        </div>

        <div class="footer-section">
          <h4>Contact Info</h4>
          <div class="contact-details">
            <div class="contact-item">
              <span class="contact-icon">📞</span>
              <div>
                <p>(555) 123-4567</p>
                <small>Mon-Fri: 9AM-6PM</small>
              </div>
            </div>
            <div class="contact-item">
              <span class="contact-icon">✉️</span>
              <div>
                <p>info@aflcservices.com</p>
                <small>24-hour response</small>
              </div>
            </div>
            <div class="contact-item">
              <span class="contact-icon">📍</span>
              <div>
                <p>123 Wellness Way, Suite 200</p>
                <small>Your City, ST 12345</small>
              </div>
            </div>
          </div>

          <div class="booking-reminder">
            <a href="#" class="btn btn-primary">Book Appointment</a>
          </div>
        </div>
      </div>

      <div class="footer-bottom">
        <div class="footer-bottom-content">
          <p>&copy; {{ currentYear }} AFLC Services. All rights reserved.</p>
          <div class="professional-notice">
            <p>Licensed Professional Counselling Services</p>
          </div>
          <div class="emergency-notice">
            <p>
              <strong>Crisis Support:</strong> If you're experiencing a mental
              health emergency, please call 911 or visit your nearest emergency
              room. For crisis support, call the National Suicide Prevention
              Lifeline at 988.
            </p>
          </div>
        </div>
      </div>
    </div>
  </footer>
</template>

<script setup>
import { computed } from "vue";

const currentYear = computed(() => new Date().getFullYear());

const scrollTo = (elementId) => {
  const element = document.getElementById(elementId);
  if (element) {
    element.scrollIntoView({ behavior: "smooth" });
  }
};
</script>

<style scoped>
.footer {
  background: linear-gradient(135deg, #4d5d44 0%, #3a4633 100%);
  color: white;
}

.footer-content {
  display: grid;
  grid-template-columns: 2fr 1fr 1fr 1.5fr;
  gap: 3rem;
  padding: 4rem 0 2rem;
}

.footer-section h3 {
  color: #e8e4a6;
  font-size: 1.8rem;
  margin-bottom: 0.5rem;
}

.footer-tagline {
  color: #bdc3c7;
  font-style: italic;
  margin-bottom: 1rem;
}

.footer-description {
  line-height: 1.6;
  color: #ecf0f1;
  margin-bottom: 1.5rem;
}

.footer-quote {
  background: rgba(255, 255, 255, 0.1);
  padding: 1rem;
  border-radius: 10px;
  border-left: 3px solid #e8e4a6;
}

.footer-quote p {
  font-style: italic;
  color: #e8e4a6;
  text-align: center;
}

.footer-section h4 {
  color: #e8e4a6;
  font-size: 1.2rem;
  margin-bottom: 1rem;
  padding-bottom: 0.5rem;
  border-bottom: 2px solid #e8e4a6;
}

.footer-links {
  list-style: none;
  padding: 0;
}

.footer-links li {
  margin-bottom: 0.5rem;
}

.footer-links a {
  color: #bdc3c7;
  text-decoration: none;
  transition: color 0.3s ease;
}

.footer-links a:hover {
  color: #e8e4a6;
}

.contact-details {
  display: flex;
  flex-direction: column;
  gap: 1rem;
  margin-bottom: 2rem;
}

.contact-item {
  display: flex;
  align-items: flex-start;
  gap: 0.5rem;
}

.contact-icon {
  font-size: 1.2rem;
  margin-top: 0.2rem;
}

.contact-item p {
  color: #ecf0f1;
  margin-bottom: 0.2rem;
}

.contact-item small {
  color: #bdc3c7;
  font-size: 0.9rem;
}

.booking-reminder {
  text-align: center;
}

.footer-bottom {
  border-top: 1px solid rgba(255, 255, 255, 0.1);
  padding: 2rem 0;
}

.footer-bottom-content {
  text-align: center;
  color: #bdc3c7;
}

.footer-bottom-content > p {
  margin-bottom: 1rem;
  font-size: 0.9rem;
}

.professional-notice {
  margin-bottom: 1rem;
}

.professional-notice p {
  font-size: 0.9rem;
  color: #95a5a6;
}

.emergency-notice {
  background: rgba(231, 76, 60, 0.1);
  border: 1px solid rgba(231, 76, 60, 0.3);
  border-radius: 8px;
  padding: 1rem;
  margin-top: 1rem;
}

.emergency-notice p {
  font-size: 0.9rem;
  line-height: 1.5;
  color: #ecf0f1;
}

.emergency-notice strong {
  color: #e74c3c;
}

@media (max-width: 768px) {
  .footer-content {
    grid-template-columns: 1fr;
    gap: 2rem;
    padding: 2rem 0 1rem;
  }

  .footer-section h3 {
    font-size: 1.5rem;
  }

  .contact-details {
    margin-bottom: 1rem;
  }

  .booking-reminder {
    margin-top: 1rem;
  }

  .emergency-notice {
    padding: 0.8rem;
  }
}
</style>
