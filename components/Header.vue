<template>
  <header>
    <div class="header-container">
      <div class="logo-section">
        <img src="/lg2.png" class="logo-image">
      </div>
      <div class="burger-icon" @click="toggleMenu">&#9776;</div>
      <nav v-show="isMenuOpen" class="nav-menu">
        <ul>
          <li><nuxt-link to="/#section1" class="nav-link">Наши услуги</nuxt-link></li>  
          <li><nuxt-link to="/#section4" class="nav-link">Галерея работ</nuxt-link></li>
          <li><nuxt-link to="/#section3" class="nav-link">FAQ</nuxt-link></li>
          <li><nuxt-link to="/#section2" class="nav-link">Контакты</nuxt-link></li>
        </ul>
      </nav>
      <div class="contact-section">
        <div class="contacts">
          <div class="contact-item">
            <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" fill="currentColor" class="w-6 h-6 contact-icon">
              <path fill-rule="evenodd" d="M1.5 4.5a3 3 0 0 1 3-3h1.372c.86 0 1.61.586 1.819 1.42l1.105 4.423a1.875 1.875 0 0 1-.694 1.955l-1.293.97c-.135.101-.164.249-.126.352a11.285 11.285 0 0 0 6.697 6.697c.103.038.25.009.352-.126l.97-1.293a1.875 1.875 0 0 1 1.955-.694l4.423 1.105c.834.209 1.42.959 1.42 1.82V19.5a3 3 0 0 1-3 3h-2.25C8.552 22.5 1.5 15.448 1.5 6.75V4.5Z" clip-rule="evenodd" />
            </svg>
            <h2>+375 (29) 846-44-60</h2>
          </div>
          <div class="contact-item">
            <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" fill="currentColor" class="w-6 h-6 contact-icon">
              <path fill-rule="evenodd" d="M1.5 4.5a3 3 0 0 1 3-3h1.372c.86 0 1.61.586 1.819 1.42l1.105 4.423a1.875 1.875 0 0 1-.694 1.955l-1.293.97c-.135.101-.164.249-.126.352a11.285 11.285 0 0 0 6.697 6.697c.103.038.25.009.352-.126l.97-1.293a1.875 1.875 0 0 1 1.955-.694l4.423 1.105c.834.209 1.42.959 1.42 1.82V19.5a3 3 0 0 1-3 3h-2.25C8.552 22.5 1.5 15.448 1.5 6.75V4.5Z" clip-rule="evenodd" />
            </svg>
            <h2>+375 (25) 573-35-21</h2>
          </div>
        </div>
        <button class="button" @click="emit('changeModal')">Вызвать замерщика</button>
      </div>
    </div>
  </header>
</template>

 <script setup>
 import { defineEmits, ref } from 'vue';
 const emit = defineEmits(['changeModal']);
 const isMenuOpen = ref(false);
 function toggleMenu() {
   isMenuOpen.value = !isMenuOpen.value;
 }
</script>

<style scoped>
  header {
    width: 100%;
    background-color: #070654; 
    color: #ffffff; 
    padding-top: 20px;
    padding-bottom: 20px;
    box-shadow: 0px 2px 5px rgba(0, 0, 0, 0.1);
    transition: 0.3s;
    margin-bottom: 40px;
  }

  .header-container {
    display: flex;
    justify-content: space-between;
    align-items: center;
    max-width: 100%;
    padding: 0 20px;
  }

  .logo-section {
    display: flex;
    align-items: center;
  }

  .logo-image {
    position: absolute;
    margin-bottom: 40px;
    height: 400px;
    width: 400px;
  }

  nav {
    display: flex;
    justify-content: center;
    align-items: center;
    margin-left: auto;
  }

  nav ul {
    display: flex;
    justify-content: center; 
    list-style-type: none;

  }

  nav li {
    font-size: 16px;
    margin-right: 30px;
    position: relative;
  }

  .nav-link {
    color: #ffffff; 
    text-decoration: none;
    transition: color 0.3s;
  }

  .nav-link:hover {
    color: #2163B2; 
  }

  li::before {
    content: '';
    position: absolute;
    width: 0%;
    height: 2px;
    background-color: #2163B2;
    bottom: 0;
    left: 0;
    transition: 0.3s;
    left: 50%; 
    transform: translateX(-50%); 
  }

  li:hover::before {
    width: 100%;
  }

  .contact-section {
    display: flex;
    align-items: center;
  }

  .contacts {
    display: flex;
    flex-direction: column;
    margin-right: 20px;
  }

  .contact-item {
    display: flex;
    align-items: center;
    margin-bottom: 10px;
  }

  .contact-icon {
    width: 24px;
    height: 24px;
    margin-right: 8px;
    fill: #ffffff; 
  }

  h2 {
    margin: 0;
    font-size: 16px;
    color: #ffffff; 
  }

  .button {
    background-color: #2163B2; 
    color: #ffffff; 
    border: none;
    cursor: pointer;
    padding: 12px 18px;
    border-radius: 15px;
    transition: 0.3s, color 0.3s;
  }

  .button:hover {
    background-color: #174580; 
    box-shadow: 0 2px 4px rgba(0, 0, 0, 0.2);
  }
  .burger-icon {
  display: none;
  cursor: pointer;
  color: #ffffff;
  font-size: 24px;
}
@media (max-width: 1440px){
  .logo-image {
    height: 350px;
    width: 350px;

  }
}
  @media (max-width: 1220px){
  .logo-image {
    height: 270px;
    width: 270px;
  }
  nav li {
    font-size: 14px;
    margin-right: 25px;
  }

  .contacts {
    display: flex;
    flex-direction: column;
    margin-right: 10px;
  }

  .contact-icon {
    width: 20px;
    height: 20px;
    margin-right: 6px;
  }

  h2 {
    font-size: 12px;
  }
  .button {
    padding: 10px 16px;
    border-radius: 15px;
    font-size: 12px;
  }


}
@media (min-width: 998px) {
  .nav-menu {
    display: flex !important; 
  }

  .burger-icon {
    display: none; 
  }
}
@media (max-width: 998px) {
  .header-container {
  display: flex;
  align-items: center;
  justify-content: space-between; 
  }
.logo-section {
  flex: 1; 
  display: flex;
  align-items: center;
  justify-content: flex-start; 
}

.logo-image {
  height: 270px;
  width: 270px;
}

.contact-section {
  flex: 2; 
  display: flex;
  align-items: center;
  justify-content: center; 
}

.contacts {
  display: flex;
  flex-direction: column;
  margin-right: 20px;
}

.burger-icon {
  display: block;
  position: absolute;
  right: 20px; 
  }

  .nav-menu {
    display: flex;
    position: absolute;
    flex-direction: column;
    top: 80px; 
    left: 0;
    background-color: #ffffff;
    padding: 10px;
    width: 100%;
    box-shadow: 0px 5px 15px rgba(0, 0, 0, 0.1);
    z-index: 9999;
  }

  .nav-menu ul {
    list-style-type: none;
    padding: 0;
    display: flex;
    flex-direction: column;
  }

  .nav-menu li {
    margin-bottom: 10px;
  }

  .nav-menu .nav-link {
    color: black;
    text-decoration: none;
    font-size: 18px;
    transition: color 0.3s;
  }

  .nav-menu .nav-link:hover {
    color: #2163B2;
  }
}

@media (max-width: 768px) {
  .nav-menu .nav-link {
    font-size: 16px;
  }
  .logo-image {
  height: 200px;
  width: 200px;
  }
  .contact-icon {
  width: 10px;
  height: 10px;
  margin-right: 4px;
  }

  h2 {
  font-size: 8px;
  }
  .button {
    padding: 8px 14px;
    border-radius: 15px;
    font-size: 10px;
  }


}

@media (max-width: 520px){
  .logo-image {
  height: 150px;
  width: 150px;
  }
 
}
@media (max-width: 480px) {
  .logo-image {
  height: 125px;
  width: 125px;
  }
  .contact-icon {
  width: 10px;
  height: 10px;
  margin-right: 4px;
  }

  h2 {
  font-size: 6px;
  }
  .button {
    padding: 8px 14px;
    border-radius: 15px;
    font-size: 8px;
  }

}
@media (max-width: 320px){

}

</style>