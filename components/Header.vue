<template>
  <header>
    <div class="header-container">
      <div class="left-section">
        <img src="/logo.png">
        <div class="logo-text">Sky Home</div>
      </div>
      <div class="contacts">
        <img src="/MTS.png">
        <h2>+375 (29) 8464460</h2>
        <img src="/A1.png">
        <h2>+375 (25) 57335215</h2>
      </div>
      <button class="button" @click="emit('changeModal')">Вызвать замерщика</button>
    </div>
    
    <nav>
      <ul>
        <li><nuxt-link to="/" class="nav-link">Каталог потолков</nuxt-link></li>
        <li><nuxt-link to="/" class="nav-link">Цены</nuxt-link></li>
        <li><nuxt-link to="/" class="nav-link">О компании</nuxt-link></li>
        <li><nuxt-link to="/" class="nav-link">Галерея работ</nuxt-link></li>
        <li><nuxt-link to="/" class="nav-link">FAQ</nuxt-link></li>
        <li><nuxt-link to="/" class="nav-link">Контакты</nuxt-link></li>
      </ul>
    </nav>
  </header>
</template>

<script setup>
const emit = defineEmits(['changeModal']);
</script>

<style scoped>
header {
  background-color: white;
  color: black;
  padding: 10px;
}

.header-container {
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.left-section {
  display: flex;
  align-items: center;
  margin-left: 100px;
}

.logo-text {
  font-size: 32px;
}

nav {
  display: flex;
  justify-content: flex-end;
  margin-top: 10px;
}

ul {
  list-style-type: none;
  padding: 0;
  margin: 0;
  display: flex;
}

li {
  font-size: 16px;
  margin-right: 50px;
}

a, .button {
  color: black;
  text-decoration: none;
  font-size: 16px;
  transition: color 0.3s, background-color 0.3s; 
}

.button {
  background-color: #2163B2;
  color: white;
  border: none;
  cursor: pointer;
  padding: 15px 18px;
  border-radius: 15px;
  margin-top: 10px;
}

.button:hover {
  background-color: #222222; 
}

.nav-link:hover {
  color: #2163B2; 
}

.contacts {
  display: flex;
  align-items: center;
}

.contacts img {
  margin-right: 10px;
  margin-left: 40px;
}
</style>