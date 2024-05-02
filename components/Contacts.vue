<template>
  <section ref="section2" id="section2" class="contacts-section">
    <div class="contact-section">
      <h1>Контакты</h1>
      <div class="flex-container">
        <div class="form-section">
          <div class="modal">
            <form>
              <h2>Оставить заявку</h2>
              <input v-model="name" placeholder="Ваше имя" required>
              <input v-model="phoneNumber" placeholder="Номер телефона" required type="tel">
              <button type="submit">Отправить заявку</button>
            </form>
          </div>
        </div>
        <div class="contacts">
          <div class="contact-items">
            <div class="contact-item">
              <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" fill="currentColor" class="w-6 h-6 contact-icon">
                <path fill-rule="evenodd" d="M1.5 4.5a3 3 0 0 1 3-3h1.372c.86 0 1.61.586 1.819 1.42l1.105 4.423a1.875 1.875 0 0 1-.694 1.955l-1.293.970c-.135.101-.164.249-.126.352a11.285 11.285 0 0 0 6.697 6.697c.103.038.25.009.352-.126l.970-1.293a1.875 1.875 0 0 1 1.955-.694l4.423 1.105c.834.209 1.42.959 1.42 1.82V19.5a3 3 0 0 1-3 3h-2.25C8.552 22.5 1.5 15.448 1.5 6.75V4.5Z" clip-rule="evenodd" />
              </svg>
              <h3>+375 (29) 8464460</h3>
            </div>
            <div class="contact-item">
              <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" fill="currentColor" class="w-6 h-6 contact-icon">
                <path fill-rule="evenodd" d="M1.5 4.5a3 3 0 0 1 3-3h1.372c.86 0 1.61.586 1.819 1.42l1.105 4.423a1.875 1.875 0 0 1-.694 1.955l-1.293.970c-.135.101-.164.249-.126.352a11.285 11.285 0 0 0 6.697 6.697c.103.038.25.009.352-.126l.970-1.293a1.875 1.875 0 0 1 1.955-.694l4.423 1.105c.834.209 1.42.959 1.42 1.82V19.5a3 3 0 0 1-3 3h-2.25C8.552 22.5 1.5 15.448 1.5 6.75V4.5Z" clip-rule="evenodd" />
              </svg>
              <h3>+375 (25) 5733521</h3>
            </div>
            <div class="social-item">
              <a href="https://www.instagram.com/sky_home_grodno/">
              
              </a>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
  const name = ref('');
  const phoneNumber = ref('');
</script>

<style scoped>
.contacts-section {
  text-align: center;
  padding: 20px;
}

h1 {
  font-family: 'Roboto', sans-serif;
  font-size: 30px;
  margin-bottom: 30px;
  color: #333;
}

.contact-section {
  max-width: 800px;
  margin: 0 auto;
}

.flex-container {
  display: flex;
  justify-content: space-between;
}

.form-section {
  width: 100%;
  padding: 10px; 
}

.modal {
  background-color: #f5f5f5;
  padding: 20px;
  border-radius: 10px;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
}

.contacts {
  width: 40%;
}

.contact-items {
  display: flex;
  flex-direction: column;
  align-items: flex-start;
}

.contact-item {
  display: flex;
  align-items: center;
  margin-bottom: 15px; 
  background-color: #fff;
  padding: 15px;
  border-radius: 8px;
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
}

.contact-icon {
  width: 24px;
  height: 24px;
  margin-right: 8px;
  fill: #2163b2;
}

input {
  width: 100%;
  margin-bottom: 10px;
  padding: 12px;
  box-sizing: border-box;
  border: 1px solid #ccc;
  border-radius: 8px;
  font-size: 14px;
}

button {
  background-color: #2163b2;
  color: white;
  border: none;
  cursor: pointer;
  padding: 12px 18px;
  border-radius: 15px;
  font-size: 14px;
  transition: 0.3s;
}

button:hover {
  background-color: #174580;
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.2);
}
</style>

