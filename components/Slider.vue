<template>
  <div class="swiper-container">
    <div class="swiper-wrapper">
      <div class="swiper-slide">
        <img src="/slide2.jpg" alt="Slide 1">
      </div>
      <div class="swiper-slide">
        <img src="/slide2.jpg" alt="Slide 2">
      </div>
      <div class="swiper-slide">
        <img src="/slide2.jpg" alt="Slide 3">
      </div>
    </div>
    <div class="swiper-pagination"></div> 
    <div class="swiper-button-next"></div>
    <div class="swiper-button-prev"></div>
  </div>
</template>

<script>
import Swiper from 'swiper/bundle';
import 'swiper/swiper-bundle.css';

export default {
  mounted() {
    this.initializeSwiper();
  },
  methods: {
    initializeSwiper() {
      new Swiper('.swiper-container', {
        loop: true,
        navigation: {
          nextEl: '.swiper-button-next',
          prevEl: '.swiper-button-prev',
        },
        pagination: {
          el: '.swiper-pagination',
          clickable: true,
        },
        autoplay: {
          delay: 5000,
          disableOnInteraction: false,
        },
      });
    },
  },
};
</script>
<style >
.swiper-container {
  width: 100%;
  height: 100%;
  overflow: hidden;
}

.swiper-slide {
  text-align: center;
  font-size: 18px;
  background-color: aliceblue;
  display: flex;
  justify-content: center;
  align-items: center;
}

.swiper-slide img {
  width: 58%;
  object-fit: cover;
}

.swiper-pagination {
  position: relative;
  bottom: 10px;
  left: 0;
  width: 100%;
  text-align: center;
  margin-top: 10px;
}

.swiper-pagination-bullet {
  width: 15px !important;
  height: 15px !important;
  display: inline-block;
  margin: 0 8px;
  background-color: #2163B2 !important; 
}

.swiper-button-next,
.swiper-button-prev {
  right: 140px !important;
  left: auto;
}

.swiper-button-prev,
.swiper-rtl .swiper-button-next {
  left: 140px !important;
  right: auto;
}

@media (max-width: 1220px) {
  .swiper-slide img {
    width: 70%;
  }

  .swiper-button-next,
  .swiper-button-prev {
    right: 100px !important;
    left: auto;
  }

  .swiper-button-prev,
  .swiper-rtl .swiper-button-next {
    left: 100px !important;
    right: auto;
  }
}
@media (max-width: 998px){
  .swiper-button-next,
  .swiper-button-prev {
    display: none;
  }
}

@media (max-width: 768px) {
  .swiper-slide img {
    width: 80%;
  }

}


@media (max-width: 480px) {
  .swiper-slide img {
    width: 90%;
  }
}


</style>