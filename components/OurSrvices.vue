<template>
  <section ref="section1" id="section1" class="services-section">
    <h1>Наши услуги</h1>
    <div class="service-grid">
      <div v-for="service in services" :key="service.id" class="service-card">
        <img v-if="service.image" :src="service.image" :alt="service.title" class="service-image">
        <div class="card-content">
          <h2>{{ service.title }}</h2>
          <p>{{ service.description }}</p>
          <button class="button" @click="emit('changeModal')">Узнать цену</button>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
const emit = defineEmits(['changeModal']);
</script>

<script>
export default {
  data() {
    return {
      services: [
          { id: 1, title: "Световые линии", description: "Световые линии - это эффективный и стильный способ освещения, который при правильном подходе может стать важным элементом вашего интерьера.", image: "service1.jpg" },
          { id: 2, title: "Световые линии", description: "Световые линии - это эффективный и стильный способ освещения, который при правильном подходе может стать важным элементом вашего интерьера.", image: "service1.jpg" },
          { id: 3, title: "Световые линии", description: "Световые линии - это эффективный и стильный способ освещения, который при правильном подходе может стать важным элементом вашего интерьера.", image: "service1.jpg" },
          { id: 4, title: "Световые линии", description: "Световые линии - это эффективный и стильный способ освещения, который при правильном подходе может стать важным элементом вашего интерьера.", image: "service1.jpg" },
          { id: 5, title: "Световые линии", description: "Световые линии - это эффективный и стильный способ освещения, который при правильном подходе может стать важным элементом вашего интерьера.", image: "service1.jpg" },
          { id: 6, title: "Световые линии", description: "Световые линии - это эффективный и стильный способ освещения, который при правильном подходе может стать важным элементом вашего интерьера.", image: "service1.jpg" },
      ]
    };
  }
};
</script>

<style scoped>
.services-section {
  text-align: center;
  padding: 100px 20px;
}

h1 {
  font-family: 'Roboto', sans-serif;
  font-size: 30px;
  margin-bottom: 30px;
  color:#333
}

.service-grid {
  display: flex;
  flex-wrap: wrap;
  justify-content: space-around;
  gap: 20px;
}

.service-card {
  width: 28%; 
  border: 1px solid #ddd;
  border-radius: 8px 8px 0 0;
  overflow: hidden;
  transition:  0.3s ease, 0.3s ease;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
}

.service-card:hover {
  transform: scale(1.05);
  box-shadow: 0 8px 16px rgba(0, 0, 0, 0.2);
}

.card-content {
  padding: 20px;
}

.service-image {
  width: 100%;
  border-radius: 8px;
  margin-bottom: 15px;
}

h2 {
  font-size: 20px; 
  margin-bottom: 10px;
  color: #333;
}

p {
  color: #666;
  margin-bottom: 15px;
}

.button {
  background-color: #2163B2;
  color: white;
  border: none;
  cursor: pointer;
  padding: 12px 18px;
  border-radius: 15px;
  font-size: 14px; 
  transition: 0.3s;
}

.button:hover {
  background-color: #174580;
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.2);
}
@media (max-width: 1440px) {
  .service-card {
    width: 30%;
  }
}

@media (max-width: 1200px) {
  .service-card {
    width: 45%; 
  }
}

@media (max-width: 998px) {
  .service-grid {
    justify-content: center;
  }
  .service-card {
    width: 60%;
  }

}

@media (max-width: 768px) {
  h1 {
    font-size: 25px;
  }
  .service-card {
    width: 80%; 
  }
  
}

@media (max-width: 480px) {
  .services-section {
    padding: 50px 10px;
  }
  h2 {
  font-size: 16px; 
  }
  p{
    font-size: 14px;
  }

}

</style>
