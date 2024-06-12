<template>
  <section ref="section3" id="section3" class="faq-section">
    <h1>Часто задаваемые вопросы</h1>
    <div class="faq-container">
      <li v-for="(faq, index) in faqList" :key="index" class="faq-item">
        <button @click="toggleAnswer(index)" class="faq-question">
          {{ faq.question }} 
          <span v-if="!faq.expanded" class="plus-icon">+</span>
          <span v-else class="minus-icon">-</span>
        </button>
        <div :class="{'faq-answer': true, 'expanded': faq.expanded}">
          <p>{{ faq.answer }}</p>
        </div>
      </li>
    </div>
  </section>
</template>

<script>
export default {
  data() {
    return {
      faqList: [
        { question: "Сколько стоит выезд замерщика?", answer: "Данная услуга абсолютно бесплатна и ни к чему вас не обязывает.", expanded: false },
        { question: "Сначала клеят обои или ставят потолок?", answer: "Можно устанавливать как до, так и после поклейки обоев. Но есть нюансы, например, при наличии красного кирпича. В этом случае лучше сначала установить натяжной потолок.", expanded: false },
        { question: "Как узнать стоимость натяжного потолка с установкой", answer: "Свяжитесь с нами, мы озвучим примерную сумму монтажа с материалом. Для точной стоимости оставьте заявку на расчет на нашем сайте.", expanded: false },
        { question: "Какой потолок лучше установить? Матовый или глянец?", answer: "На вкус и цвет нет товарища. Мы даем советы, но выбор остается за вами. Белое матовое полотно освежит помещение, глянцевые потолки увеличивают визуально высоту стен.", expanded: false },
      ],
    };
  },
  methods: {
    toggleAnswer(index) {
      this.faqList[index].expanded = !this.faqList[index].expanded;
    },
  },
};
</script>

<style scoped>
li {
  list-style: none;
}
h1 {
  font-family: 'Roboto', sans-serif;
  font-size: 30px;
  margin-bottom: 30px;
  color: #333;
  text-align: center;
}
.faq-section {
  margin-top: 100px;
  margin-bottom: 100px;
  font-family: 'Roboto', sans-serif;
}
.faq-container {
  max-width: 600px;
  margin: 0 auto;
  background-color: #f5f5f5;
  padding: 30px;
  border-radius: 10px;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
}
.faq-item {
  margin-bottom: 20px;
  margin-top: 20px;
}
.faq-question {
  position: relative;
  background-color: #2163B2;
  color: #fff;
  padding: 15px;
  cursor: pointer;
  border-radius: 8px;
  border: none;
  width: 100%;
  text-align: left;
  font-size: 18px;
  transition: 0.3s, color 0.3s;
}
.faq-question:hover {
  background-color: #174580;
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.2);
}
.plus-icon,
.minus-icon {
  position: absolute;
  top: 50%;
  right: 15px;
  transform: translateY(-50%);
}
.faq-answer {
  max-height: 0;
  overflow: hidden;
  transition: 0.5s ease-in-out;
}
.faq-answer.expanded {
  max-height: 150px; 
}
.faq-answer p {
  margin: 0;
  padding: 15px;
  background-color: #f0f0f0;
  border-radius: 8px;
  font-size: 18px;
}

@media (max-width: 998px) {
  .faq-container {
    max-width: 550px;
  }
}
@media (max-width: 768px) {
  .faq-container {
    max-width: 450px;
  }
}
@media (max-width: 520px) {
  .faq-container {
    max-width: 400px;
  }
  .faq-question {
    font-size: 16px;
  }
  .faq-answer p {
    font-size: 16px;
  }
}
@media (max-width: 480px) {
  .faq-container {
    max-width: 300px;
  }
  .faq-question {
    font-size: 13px;
  }
  .faq-answer p {
    font-size: 13px;
  }
}
@media (max-width: 375px) {
  .faq-container {
    max-width: 300px;
  }
}
</style>
