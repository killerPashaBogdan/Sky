<template>
  <section ref="section5" id="section5" class="review-section">
    <h1>Отзывы от клиентов</h1>
  <div class="review-container">
  <div class="review-slider">
    <Swiper
      :slides-per-view="3"
      :space-between="30"
      :pagination="{ clickable: true }"
      :navigation="true"
      :autoplay="{ delay: 10000, disableOnInteraction: false }"
      :breakpoints="{
        320: {
          slidesPerView: 1,
          spaceBetween: 20,
        },
        768: {
          slidesPerView: 2,
          spaceBetween: 20,
        },
        1220: {
          slidesPerView: 3,
          spaceBetween: 30,
        },
      }"
    >
      <SwiperSlide v-for="(review, index) in reviews" :key="index">
        <div class="review-card">
          <h3>{{ review.author }}</h3>
          <div class="stars">
            <span v-for="n in review.rating" :key="n" class="star">★</span>
          </div>
          <p>{{ review.text }}</p>
        </div>
      </SwiperSlide>
      <div class="swiper-pagination"></div>
    </Swiper>
  </div>
</div>
</section>
</template>

<script setup>
import { Swiper, SwiperSlide } from 'swiper/vue';
import 'swiper/swiper-bundle.css';

const reviews = [
  {
    author: 'Наталья Юрченко',
    text: 'Отличные ребята!!Настоятельно рекомендую, быстрый отклик, без лишних, слов))Сделали всё быстро и качественно, очень довольна результатом! Благополучия и процветания!🤗👍',
    rating: 5,
  },
  {
    author: 'Марта Антанович',
    text: 'Здравствуйте, хочу выразитьОГРОМНУЮ БЛАГОДАРНОСТЬ за ваш труд и за качественно выполненную работу!🙏Заказав у вас потолки, у нас ни на минуту не вызвало сомнений в вашем профессионализме!!! Вы - мастера с большой буквы!!!! Отдельное спасибо вам, за что что умеете слушать и слышать все пожелания клиента и потом это все воплощаете в реальность!!! Ваш результат работы - это просто кайф для меня 😍теперь хожу по квартире и не могу налюбоваться нашими оболденными потолкам, они просто огонь 🔥🔥🔥Ещё раз, огромное спасибо вам!!!!🙏🙏🙏',
    rating: 5,
  },
  {
    author: 'Лариса Лисовская',
    text: 'Благодарны Вам за красивые потолки!!!За качество!!!Все сделано в срок! Быстро! Профессионально!!!Спасибо огромное!!!!Ребята, вы лучшие!!!',
    rating: 5,
  },
  {
    author: 'Иван Иванов',
    text: 'Хочу сказать большое спасибо мастерам( Паше и Паше), которые вчера делали потолок на ул.Дзержинского. Работа выполнена качественно, быстро, профессионально. Просто Класс!!!Хочется и в дальнейшем с вами сотрудничать ( хотя в нынешней ситуации это бывает очень редко).Огромная благодарность за работу!!!',
    rating: 5,
  },
  {
    author: 'Егор Жук',
    text: 'Потолки супер!!Профессионалы своего дела!!Потолки огонь!!🔥🔥🔥🔥',
    rating: 5,
  },
];
</script>

<style scoped>
.swiper-button-next,
.swiper-button-prev {
  right: 140px !important;
  left: auto;
}
.swiper-slide {
  background-color: #fff;
}
 .review-section {
    margin-top: 100px;
    margin-bottom: 100px;
    padding: 60px;

  }
  h1 {
  font-family: 'Roboto', sans-serif;
  font-size: 30px;
  margin-bottom: 30px;
  color: #333;
  text-align: center;
}
.review-slider {
  padding: 40px 0;
}

.review-card {
  background-color: #fff;
  border: 1px solid #ddd;
  padding: 20px;
  border-radius: 5px;
  text-align: left;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
  height: 440px; 
  width: 500px; 
  box-sizing: border-box;
  transition:  0.3s ease, 0.3s ease;
}

.review-card:hover{
  box-shadow: 0 8px 16px rgba(0, 0, 0, 0.2);
}
.review-card h3 {
  margin-bottom: 10px;
  font-size: 18px;
  font-weight: bold;
}

.review-card .stars {
  color: #ffa500;
  margin-bottom: 10px;
}

.review-card .star {
  margin-right: 2px;
}

.review-card p {
  font-size: 16px;
  color: #333;
}

.swiper-pagination {
  margin-top: 10px;
}
@media (max-width: 1440px){
.review-card h3 {
  font-size: 16px;
}

.review-card p {
  font-size: 14px;
  color: #333;
}

}
@media (max-width: 520px){
  .review-card h3 {
  font-size: 14px;
}
.review-card p {
  font-size: 13px;

}
.review-card .stars {
  margin-bottom: 1px;
}
}
</style>