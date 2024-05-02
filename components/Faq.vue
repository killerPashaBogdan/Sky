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
            <p v-if="faq.expanded" class="faq-answer">{{ faq.answer }}</p>
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
          { question: "Сначала клеят обои или ставят потолок?", answer: "Можно устанавливать как до, так и после поклейки обоев. Но есть нюансы, например, при наличии красного кирпича. В этом случае лучше сначала установить натяжной потолок." , expanded: false },
          { question: "Как узнать стоимость натяжного потолка с установкой", answer: "Свяжитесь с нами, мы озвучим примерную сумму монтажа с материалом. Для точной стоимости оставьте заявку на расчет на нашем сайте." , expanded: false },
          { question: "Какой потолок лучше установить? Матовый или глянец?", answer: "На вкус и цвет нет товарища. Мы даем советы, но выбор остается за вами. Белое матовое полотно освежит помещение, глянцевые потолки увеличивают визуально высоту стен." , expanded: false },
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
  li{
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
  }
  
  .plus-icon,
  .minus-icon {
    position: absolute;
    top: 50%;
    right: 15px; 
    transform: translateY(-50%);
  }
  
  .faq-answer {
    margin-top: 10px;
    padding: 15px;
    background-color: #f0f0f0;
    border: none;
    border-radius: 8px;
    font-size: 18px;
  }
  
  </style>
  