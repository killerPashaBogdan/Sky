<template>
  <section ref="section4" id="section4" class="gallery-section">
    <h1>Галерея работ</h1>
    <div class="gallery">
      <div v-for="(image, index) in galleryImages" :key="index" class="gallery-item">
        <img
          v-if="index < visibleImages"
          :src="image.src"
          :alt="image.alt"
          @click="openModal(index)"
          loading="lazy"
          class="large-image"
        />
      </div>
    </div>
    <div v-if="modalOpened" class="modal" @click.self="closeModal">
      <div class="modal-content">
        <span class="close" @click="closeModal">&times;</span>
        <div class="swiper-container" v-if="modalOpened">
          <div class="swiper-wrapper">
            <div v-for="(image, index) in galleryImages" :key="index" class="swiper-slide">
              <img
                v-if="index < visibleImages"
                :src="image.src"
                :alt="image.alt"
                class="full-screen-image"
                loading="lazy"
              />
            </div>
          </div>
          <div class="swiper-button-prev"></div>
          <div class="swiper-button-next" @click="loadNext"></div>
        </div>
      </div>
    </div>
    <button v-if="!modalOpened" @click="loadMore" class="gallery-button">{{ visibleImages < galleryImages.length ? 'Загрузить еще' : 'Свернуть' }}</button>
  </section>
</template>


<script>
import Swiper from 'swiper';
export default {
  data() {
    return {
      galleryImages: [
        { src: "/1.jpg", loaded: false },
        { src: "/2.jpg", loaded: false },
        { src: "/3.jpg", loaded: false },
        { src: "/4.jpg", loaded: false },
        { src: "/5.jpg", loaded: false },
        { src: "/6.jpg", loaded: false },
        { src: "/7.jpg", loaded: false },
        { src: "/8.jpg", loaded: false },
        { src: "/9.jpg", loaded: false },
        { src: "/10.jpg", loaded: false },
        { src: "/11.jpg", loaded: false },
      ],
      visibleImages: 6,
      modalOpened: false,
      currentIndex: 0,
      swiper: null,
    };
  },
  methods: {
  openModal(index) {
    this.modalOpened = true;
    this.currentIndex = index;
    this.$nextTick(() => {
      this.initSwiper();
    });
  },
  closeModal() {
    this.modalOpened = false;
    this.destroySwiper();
  },
  initSwiper() {
    this.swiper = new Swiper('.swiper-container', {
      navigation: {
        nextEl: '.swiper-button-next',
        prevEl: '.swiper-button-prev',
      },
      initialSlide: this.currentIndex,
      on: {
        slideChange: () => {
          if (this.swiper.isEnd) {
            this.loadNext();
          }
        }
      }
    });
  },
  destroySwiper() {
    if (this.swiper) {
      this.swiper.destroy(true, true);
      this.swiper = null;
    }
  },
  loadMore() {
    if (this.visibleImages < this.galleryImages.length) {
      this.visibleImages += 6;
    } else {
      this.visibleImages = 6;
    }
  },
  loadNext() {
    const nextIndex = this.visibleImages;
    if (nextIndex < this.galleryImages.length) {
      this.visibleImages += 1;
    }
  }
  
}

};
</script>


<style scoped>
.gallery-section{
  text-align: center;
  padding: 100px 20px;
}
 h1 {
  font-family: 'Roboto', sans-serif;
  font-size: 30px;
  margin-bottom: 30px;
  color: #333;
}
button {
  background-color: #2163b2;
  color: white;
  border: none;
  cursor: pointer;
  width: 120px;
  height: 40px;
  border-radius: 15px;
  font-size: 14px;
  transition: 0.3s;
}
button:hover {
  background-color: #174580;
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.2);
}
.full-screen-image {
  max-width: 90vw;
  max-height: 90vh;
  object-fit: contain;
  cursor: pointer;
}

.large-image {
  max-width: 100%;
  height: auto;
  cursor: pointer;
  margin: 10px;
  width: 100%;
  height: 100%;
}
.gallery {
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
  padding: 0 20px; 
}

.gallery-item {
  width: calc(100% / 6 - 40px);
  margin: 20px;
  width: 230px;
  height: 230px;
}

.modal {
  display: flex;
  justify-content: center;
  align-items: center;
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-color: rgba(0, 0, 0, 0.7);
  overflow: auto;
  z-index: 999;
}

.modal-content {
  max-width: 90vw;
  max-height: 90vh;
  text-align: center;
}

.close {
  position: absolute;
  top: 10px;
  right: 10px;
  color: #fff;
  cursor: pointer;
}

@media (max-width: 1440px) {
  .gallery-item {
    width: calc(100% / 4 - 40px); 
  }

}

@media (max-width: 1200px) {
  .gallery-item {
    width: calc(100% / 3 - 40px); 
  }

}

@media (max-width: 998px) {
  .gallery-item {
    width: calc(100% / 2 - 40px); 
  }
}

@media (max-width: 768px) {
  .gallery-item {
    width: calc(100% / 2 - 20px);
  }

}

@media (max-width: 480px) {
  .gallery-section {
    padding: 50px 10px;
  }
  .gallery-item {
    width: 100%; 
    margin: 10px 0; 
  }
}
</style>