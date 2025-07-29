<template>
  <section id="about" class="section about">
    <div class="container">
      <h2 class="section-title">About AFLC Services</h2>
      <div class="about-content">
        <div class="about-text">
          <div class="intro">
            <h3>Compassionate Counselling & Support</h3>
            <p>
              At AFLC Services, we provide trauma-informed and anti-oppressive
              counselling services aimed at offering nervous-system and trauma
              education along with tools for wellness and recovery from life's
              trials and obstacles.
            </p>
          </div>

          <div class="mission">
            <h4>Our Mission</h4>
            <p>
              Our focus remains on creating a safe and supportive environment
              for individuals to navigate their healing journey and to return to
              safety and security within themselves. We believe in the power of
              compassionate care and evidence-based therapeutic approaches.
            </p>
          </div>

          <div class="approach">
            <h4>Our Approach</h4>
            <ul>
              <li>✓ Trauma-informed care principles</li>
              <li>✓ Anti-oppressive therapy practices</li>
              <li>✓ Nervous-system regulation techniques</li>
              <li>✓ Evidence-based therapeutic modalities</li>
              <li>✓ Culturally sensitive and inclusive environment</li>
            </ul>
          </div>

          <div class="credentials">
            <h4>Professional Qualifications</h4>
            <p>
              Our licensed therapists bring years of experience in trauma
              therapy, mental health counselling, and specialized therapeutic
              techniques. We are committed to ongoing education and professional
              development to provide the highest quality care.
            </p>
          </div>
        </div>

        <div class="about-image">
          <div class="therapist-card">
            <div class="therapist-photo">
              <div class="photo-placeholder">

                <span class="icon">👨‍⚕️</span>
              </div>
            </div>
            <div class="therapist-info">
              <h4>Licensed Professional Counsellor</h4>
              <p>
                Specializing in trauma therapy, anxiety, depression, and
                wellness coaching
              </p>
              <div class="certifications">
                <span class="cert">Licensed Therapist</span>
                <span class="cert">Trauma Specialist</span>
                <span class="cert">ART Certified</span>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
.about {
  background: #f8f9fa;
}

.about-content {
  display: grid;
  grid-template-columns: 2fr 1fr;
  gap: 4rem;
  align-items: start;
}

.about-text {
  display: flex;
  flex-direction: column;
  gap: 2rem;
}

.intro h3 {
  color: #4d5d44;
  font-size: 1.8rem;
  margin-bottom: 1rem;
}

.intro p {
  font-size: 1.1rem;
  line-height: 1.8;
  color: #555;
}

.mission h4,
.approach h4,
.credentials h4 {
  color: #2c3e50;
  font-size: 1.3rem;
  margin-bottom: 1rem;
  padding-bottom: 0.5rem;
  border-bottom: 2px solid #4d5d44;
  display: inline-block;
}

.mission p,
.credentials p {
  line-height: 1.7;
  color: #666;
}

.approach ul {
  list-style: none;
  padding: 0;
}

.approach li {
  padding: 0.5rem 0;
  color: #666;
  font-size: 1.1rem;
}

.therapist-card {
  background: white;
  border-radius: 20px;
  padding: 2rem;
  box-shadow: 0 10px 30px rgba(0, 0, 0, 0.1);
  text-align: center;
}

.photo-placeholder {
  width: 150px;
  height: 150px;
  background: linear-gradient(135deg, #4d5d44, #3a4633);
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
  margin: 0 auto 1.5rem;
}

.photo-placeholder .icon {
  font-size: 4rem;
}

.therapist-info h4 {
  color: #4d5d44;
  margin-bottom: 1rem;
}

.therapist-info p {
  color: #666;
  line-height: 1.6;
  margin-bottom: 1.5rem;
}

.certifications {
  display: flex;
  flex-direction: column;
  gap: 0.5rem;
}

.cert {
  background: #4d5d44;
  color: white;
  padding: 0.5rem 1rem;
  border-radius: 20px;
  font-size: 0.9rem;
  font-weight: 500;
}

@media (max-width: 768px) {
  .about-content {
    grid-template-columns: 1fr;
    gap: 2rem;
  }

  .intro h3 {
    font-size: 1.5rem;
  }

  .therapist-card {
    padding: 1.5rem;
  }

  .photo-placeholder {
    width: 120px;
    height: 120px;
  }

  .photo-placeholder .icon {
    font-size: 3rem;
  }
}
</style>
