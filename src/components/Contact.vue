<template>
  <section id="contact" class="section contact">
    <div class="container">
      <h2 class="section-title">Get In Touch</h2>
      <p class="contact-intro">
        Ready to begin your healing journey? We're here to support you every
        step of the way. Reach out to schedule a consultation or ask any
        questions you may have.
      </p>

      <div class="contact-content">
        <div class="contact-info">
          <div class="info-item">
            <div class="info-icon">📞</div>
            <div class="info-details">
              <h3>Phone</h3>
              <p>(555) 123-4567</p>
              <span>Available Mon-Fri, 9AM-6PM</span>
            </div>
          </div>

          <div class="info-item">
            <div class="info-icon">✉️</div>
            <div class="info-details">
              <h3>Email</h3>
              <p>info@aflcservices.com</p>
              <span>We respond within 24 hours</span>
            </div>
          </div>

          <div class="info-item">
            <div class="info-icon">📍</div>
            <div class="info-details">
              <h3>Location</h3>
              <p>
                Professional Office Building<br />
                123 Wellness Way, Suite 200<br />
                Your City, ST 12345
              </p>
              <span>Easy parking available</span>
            </div>
          </div>

          <div class="info-item">
            <div class="info-icon">🕒</div>
            <div class="info-details">
              <h3>Office Hours</h3>
              <p>
                Monday - Friday: 9:00 AM - 6:00 PM<br />
                Saturday: 10:00 AM - 3:00 PM<br />
                Sunday: Closed
              </p>
              <span>Emergency support available</span>
            </div>
          </div>
        </div>

        <div class="contact-form-container">
          <form @submit.prevent="submitForm" class="contact-form">
            <h3>Send us a message</h3>

            <div class="form-group">
              <label for="name">Full Name *</label>
              <input
                type="text"
                id="name"
                v-model="form.name"
                required
                placeholder="Enter your full name"
              />
            </div>

            <div class="form-row">
              <div class="form-group">
                <label for="email">Email Address *</label>
                <input
                  type="email"
                  id="email"
                  v-model="form.email"
                  required
                  placeholder="your@email.com"
                />
              </div>

              <div class="form-group">
                <label for="phone">Phone Number</label>
                <input
                  type="tel"
                  id="phone"
                  v-model="form.phone"
                  placeholder="(555) 123-4567"
                />
              </div>
            </div>

            <div class="form-group">
              <label for="service">Service of Interest</label>
              <select id="service" v-model="form.service">
                <option value="">Select a service</option>
                <option value="individual-therapy">
                  Individual Trauma Therapy
                </option>
                <option value="art-therapy">
                  Accelerated Resolution Therapy
                </option>
                <option value="wellness-presentation">
                  Mental Wellness Presentation
                </option>
                <option value="anxiety-depression">
                  Anxiety & Depression Support
                </option>
                <option value="consultation">Initial Consultation</option>
              </select>
            </div>

            <div class="form-group">
              <label for="preferred-contact">Preferred Contact Method</label>
              <div class="radio-group">
                <label class="radio-label">
                  <input
                    type="radio"
                    value="email"
                    v-model="form.preferredContact"
                  />
                  Email
                </label>
                <label class="radio-label">
                  <input
                    type="radio"
                    value="phone"
                    v-model="form.preferredContact"
                  />
                  Phone
                </label>
                <label class="radio-label">
                  <input
                    type="radio"
                    value="either"
                    v-model="form.preferredContact"
                  />
                  Either
                </label>
              </div>
            </div>

            <div class="form-group">
              <label for="message">Message *</label>
              <textarea
                id="message"
                v-model="form.message"
                required
                rows="5"
                placeholder="Tell us how we can help you or any questions you have..."
              ></textarea>
            </div>

            <div class="form-group">
              <label class="checkbox-label">
                <input type="checkbox" v-model="form.consent" required />
                I consent to being contacted about my inquiry and understand
                that my information will be kept confidential in accordance with
                privacy policies.
              </label>
            </div>

            <button
              type="submit"
              class="btn btn-primary"
              :disabled="isSubmitting"
            >
              {{ isSubmitting ? "Sending..." : "Send Message" }}
            </button>
          </form>

          <div class="booking-cta">
            <h4>Ready to Book?</h4>
            <p>
              Schedule your appointment directly through our secure booking
              system.
            </p>
            <a href="#" class="btn btn-secondary">Book Online</a>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
import { ref, reactive } from "vue";

const isSubmitting = ref(false);

const form = reactive({
  name: "",
  email: "",
  phone: "",
  service: "",
  preferredContact: "email",
  message: "",
  consent: false,
});

const submitForm = async () => {
  isSubmitting.value = true;

  // Simulate form submission
  setTimeout(() => {
    alert(
      "Thank you for your message! We will get back to you within 24 hours."
    );

    // Reset form
    Object.assign(form, {
      name: "",
      email: "",
      phone: "",
      service: "",
      preferredContact: "email",
      message: "",
      consent: false,
    });

    isSubmitting.value = false;
  }, 1000);
};
</script>

<style scoped>
.contact {
  background: #f8f9fa;
}

.contact-intro {
  text-align: center;
  font-size: 1.2rem;
  color: #666;
  max-width: 600px;
  margin: 0 auto 3rem;
  line-height: 1.6;
}

.contact-content {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 4rem;
  align-items: start;
}

.contact-info {
  display: flex;
  flex-direction: column;
  gap: 2rem;
}

.info-item {
  display: flex;
  align-items: flex-start;
  gap: 1rem;
  padding: 1.5rem;
  background: white;
  border-radius: 15px;
  box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
}

.info-icon {
  font-size: 2rem;
  width: 60px;
  text-align: center;
}

.info-details h3 {
  color: #4d5d44;
  margin-bottom: 0.5rem;
}

.info-details p {
  color: #333;
  margin-bottom: 0.5rem;
  line-height: 1.5;
}

.info-details span {
  color: #888;
  font-size: 0.9rem;
  font-style: italic;
}

.contact-form-container {
  display: flex;
  flex-direction: column;
  gap: 2rem;
}

.contact-form {
  background: white;
  padding: 2rem;
  border-radius: 20px;
  box-shadow: 0 10px 30px rgba(0, 0, 0, 0.1);
}

.contact-form h3 {
  color: #4d5d44;
  margin-bottom: 1.5rem;
  text-align: center;
}

.form-group {
  margin-bottom: 1.5rem;
}

.form-row {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 1rem;
}

.form-group label {
  display: block;
  margin-bottom: 0.5rem;
  color: #333;
  font-weight: 500;
}

.form-group input,
.form-group select,
.form-group textarea {
  width: 100%;
  padding: 0.75rem;
  border: 2px solid #e1e5e9;
  border-radius: 8px;
  font-size: 1rem;
  transition: border-color 0.3s ease;
}

.form-group input:focus,
.form-group select:focus,
.form-group textarea:focus {
  outline: none;
  border-color: #4d5d44;
}

.radio-group {
  display: flex;
  gap: 1rem;
  flex-wrap: wrap;
}

.radio-label {
  display: flex;
  align-items: center;
  gap: 0.5rem;
  cursor: pointer;
}

.radio-label input[type="radio"] {
  width: auto;
}

.checkbox-label {
  display: flex;
  align-items: flex-start;
  gap: 0.5rem;
  cursor: pointer;
  line-height: 1.5;
}

.checkbox-label input[type="checkbox"] {
  width: auto;
  margin-top: 0.25rem;
}

.booking-cta {
  background: linear-gradient(135deg, #4d5d44, #3a4633);
  color: white;
  padding: 2rem;
  border-radius: 15px;
  text-align: center;
}

.booking-cta h4 {
  margin-bottom: 1rem;
  font-size: 1.3rem;
}

.booking-cta p {
  margin-bottom: 1.5rem;
  opacity: 0.9;
}

@media (max-width: 768px) {
  .contact-content {
    grid-template-columns: 1fr;
    gap: 2rem;
  }

  .form-row {
    grid-template-columns: 1fr;
  }

  .contact-form {
    padding: 1.5rem;
  }

  .radio-group {
    flex-direction: column;
  }
}
</style>
