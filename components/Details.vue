<template>
  <div class="container">
    <h2 class="title">Натяжные потолки: красота и функциональность</h2>
    <div class="details_content">
      <div class="details_text">
        <p>Натяжные потолки - это особенное полотно, которое крепится на пластиковые или металлические профили. Они идеально гармонируют с любым дизайном интерьера, обеспечивая высокую долговечность и спрос в сфере строительства.</p>
        <p>Современные натяжные потолки занимают лидирующее положение в области дизайнерских решений. Они позволяют визуально корректировать форму помещений, эффективно скрывая недостатки строения. В эпоху технологий и гаджетов натяжные потолки становятся незаменимым решением, скрывая провода и создавая современный облик помещения.</p>
        <p>Выбирая наши натяжные потолки, вы вкладываете не только в уют своего дома, но и в долгосрочное благополучие. Наши конструкции гарантируют надежное служение на протяжении многих лет, обеспечивая высокое качество и доступные цены.</p>
      </div>
      <div class="details_steps">
        <ol class="numbered-list">
          <li>Применение натяжного потолка гарантирует эстетическую привлекательность и улучшает внешний вид интерьера. Помещение приобретает дополнительное освещение, а его размеры визуально расширяются, создавая ощущение простора.</li>
          <li>Монтаж потолка требует минимум времени и не использует клеи, что экономит ресурсы и уменьшает мусор после ремонта. Уход за ним также прост и легок.</li>
          <li>Натяжные потолки идеально скрывают габаритные конструкции, трубы, старые поверхности, а также позволяют легко прикрепить коммуникации и вытяжку.</li>
        </ol>
      </div>
    </div>
  </div>
</template>

<style scoped>
.container {
  max-width: 800px;
  margin: 0 auto;
  padding: 40px;
}

.title {
  font-family: 'Roboto', sans-serif;
  font-size: 30px;
  margin-top: 30px;
  margin-bottom: 20px;
  color:#333;
}

.details_content {
  display: flex;
  justify-content: space-between;
}

.details_text {
  width: 60%;
  color: #666;
}

.details_text p {
  margin-bottom: 20px;
  line-height: 1.6;
  color: #444; 
}

.details_steps {
  width: 35%;
}

.numbered-list {
  list-style-type: none;
  padding-left: 20px;
}

.numbered-list li {
  counter-increment: step;
  margin-bottom: 20px;
  color: #666;
}

.numbered-list li:before {
  content: counter(step);
  font-size: 24px;
  color: #2163B2;
  margin-right: 12px;
  display: inline-block;
}
@media (max-width: 1440px) {
  .container {
    padding: 30px;
  }
  .title {
    font-size: 28px;
  }
}

@media (max-width: 1200px) {
  .container {
    padding: 20px;
  }
  .title {
    font-size: 26px;
  }

}

@media (max-width: 998px) {
  .details_content {
    flex-direction: column;
  }
  .details_text,
  .details_steps {
    width: 100%;
  }
}
@media (max-width: 768px) {
  .title {
    font-size: 24px;
  }
  .numbered-list li:before {
    font-size: 22px;
  }
}

@media (max-width: 480px) {
  .container {
    padding: 10px;
  }
  .title {
    font-size: 20px;
  }
  .numbered-list li:before {
    font-size: 20px;
  }
}
</style>