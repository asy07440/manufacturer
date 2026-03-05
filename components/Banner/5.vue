<template>
  <div class="contact-wrapper">
    <div class="container">
      
      <div class="info-side">
        <h1 class="main-title">Call Us or Fill the Form</h1>
        
        <div class="info-stack">
          <div class="contact-item">
            <Smartphone :size="20" class="icon" />
            <div class="text-group">
              <span class="phone-num">646-872-4210</span>
              <p class="sub-text">Don't hesitate to contact us</p>
            </div>
          </div>

          <div class="contact-item">
            <Clock :size="20" class="icon" />
            <div class="text-group">
              <span class="phone-num">646-872-4210</span>
              <p class="sub-text">Don't hesitate to contact us</p>
            </div>
          </div>

          <div class="contact-item">
            <MapPin :size="20" class="icon" />
            <div class="text-group">
              <span class="address-label">Factory Address</span>
              <address class="address-content">
                5022 Forest Avenue<br />
                New York, 10013
              </address>
            </div>
          </div>
        </div>
      </div>

      <div class="form-side">
        <form @submit.prevent="handleSubmit" class="compact-form">
          <div class="form-grid">
            <div class="field">
              <input v-model="form.name" type="text" placeholder="Name" />
            </div>
            <div class="field">
              <input v-model="form.company" type="text" placeholder="Company" />
            </div>
            <div class="field">
              <input v-model="form.email" type="email" placeholder="E-mail Address" />
            </div>
            <div class="field">
              <input v-model="form.phone" type="tel" placeholder="Phone" />
            </div>
          </div>

          <textarea 
            v-model="form.message" 
            placeholder="How can we help?"
            rows="5"
          ></textarea>

          <button type="submit" class="btn-submit">
            Submit
          </button>
        </form>
      </div>

    </div>
  </div>
</template>

<script setup>
import { ref } from 'vue'
import { Smartphone, Clock, MapPin } from 'lucide-vue-next'

const form = ref({
  name: '',
  company: '',
  email: '',
  phone: '',
  message: ''
})

const handleSubmit = () => {
  console.log('Form Data:', form.value)
}
</script>

<style scoped>
/* Base Styles */
.contact-wrapper {
  --primary-blue: #5c67f2;
  --dark-text: #2d3e75;
  --light-gray: #94a3b8;
  
  background-color: #f8faff;
  min-height: 100vh;
  display: flex;
  align-items: center;
  justify-content: center;
  padding: 40px;
  font-family: 'Inter', -apple-system, sans-serif;
}

.container {
  display: flex;
  justify-content: space-between;
  align-items: flex-start;
  max-width: 1200px; /* Sesuai permintaan */
  width: 100%;
  gap: 100px; /* Memberikan ruang napas di layar lebar */
}

/* Sisi Kiri */
.info-side {
  flex: 0 1 400px;
}

.main-title {
  color: var(--dark-text);
  font-size: 2rem;
  font-weight: 800;
  margin-bottom: 35px;
  line-height: 1.1;
}

.info-stack {
  display: flex;
  flex-direction: column;
  gap: 20px;
}

.contact-item {
  display: flex;
  gap: 15px;
  align-items: flex-start;
}

.icon {
  color: var(--primary-blue);
  flex-shrink: 0;
}

.phone-num, .address-label {
  display: block;
  font-weight: 700;
  color: #475569;
  font-size: 1rem;
}

.sub-text, .address-content {
  color: var(--light-gray);
  font-size: 0.9rem;
  margin: 2px 0 0 0;
  font-style: normal;
  line-height: 1.5;
}

/* Sisi Kanan (Form) */
.form-side {
  flex: 1;
  max-width: 600px; /* Agar form tidak terlalu melebar meski container 1200px */
}

.compact-form {
  display: flex;
  flex-direction: column;
  gap: 15px;
}

.form-grid {
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  gap: 15px;
}

input, textarea {
  width: 100%;
  padding: 12px 18px;
  border: 1px solid #e2e8f0;
  border-radius: 10px;
  font-size: 0.9rem;
  background-color: #ffffff;
  transition: all 0.2s ease;
  box-sizing: border-box;
}

input::placeholder, textarea::placeholder {
  color: #cbd5e0;
  text-align: center;
}

input:focus, textarea:focus {
  outline: none;
  border-color: var(--primary-blue);
  box-shadow: 0 0 0 3px rgba(92, 103, 242, 0.05);
}

textarea {
  resize: none;
  padding-top: 20px;
}

.btn-submit {
  background-color: var(--primary-blue);
  color: #fff;
  border: none;
  border-radius: 50px;
  padding: 14px;
  font-weight: 600;
  font-size: 1rem;
  cursor: pointer;
  margin-top: 5px;
  transition: background 0.3s;
}

.btn-submit:hover {
  background-color: #4a54d1;
}

/* Responsive */
@media (max-width: 1024px) {
  .container {
    gap: 40px;
  }
}

@media (max-width: 768px) {
  .container {
    flex-direction: column;
    padding: 20px;
  }
  .info-side, .form-side {
    max-width: 100%;
    width: 100%;
  }
  .form-grid {
    grid-template-columns: 1fr;
  }
}
</style>