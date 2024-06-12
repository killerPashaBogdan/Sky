<template>
  <section ref="section4" id="section4" class="gallery-section">
    <h1>Галерея работ</h1>
    <div class="gallery">
      <div v-for="(image, index) in galleryImages" :key="index" class="gallery-item" @click="openImage(index)">
        <img
          :src="image.src"
          :alt="image.alt"
          loading="lazy"
          class="large-image"
        />
      </div>
    </div>
    <div v-if="showFullscreen" class="fullscreen-overlay" @click="close">
      <div class="image-container" @click.stop>
        <img :src="galleryImages[currentIndex].src" :alt="galleryImages[currentIndex].alt" class="fullscreen-image" />
        <button class="close-button" @click="close">×</button>
        <button class="nav-button prev" @click="prev">‹</button>
        <button class="nav-button next" @click="next">›</button>
      </div>
    </div>
  </section>
</template>


<script>
import { ref } from 'vue'

export default {
  setup() {
    const galleryImages = [
      { src: "/photo1.jpg", alt: "Image 1" },
      { src: "/photo2.jpg", alt: "Image 2" },
      { src: "/photo3.jpg", alt: "Image 3" },
      { src: "/photo4.jpg", alt: "Image 4" },
      { src: "/photo5.jpg", alt: "Image 5" },
      { src: "/photo6.jpg", alt: "Image 6" },
      { src: "/photo7.jpg", alt: "Image 7" },
      { src: "/2.jpg", alt: "Image 8" },
      { src: "/9.jpg", alt: "Image 9" },
      { src: "/10.jpg", alt: "Image 10" },
    ]

    const showFullscreen = ref(false)
    const currentIndex = ref(0)

    const closeOverlay = (event) => {
      if (event.target.classList.contains('fullscreen-overlay')) {
        showFullscreen.value = false
      }
    }
    const openImage = (index) => {
      currentIndex.value = index
      showFullscreen.value = true
    }

    const close = () => {
      showFullscreen.value = false
    }

    const next = (event) => {
      event.stopPropagation()
      currentIndex.value = (currentIndex.value + 1) % galleryImages.length
    }

    const prev = (event) => {
      event.stopPropagation()
      currentIndex.value = (currentIndex.value - 1 + galleryImages.length) % galleryImages.length
    }

    return {
      galleryImages,
      showFullscreen,
      currentIndex,
      openImage,
      close,
      next,
      prev,
      closeOverlay,
    }
  }
}

</script>

<style scoped>
.gallery-section {
  text-align: center;
  padding: 100px 20px;
}

h1 {
  font-family: 'Roboto', sans-serif;
  font-size: 30px;
  margin-bottom: 30px;
  color: #333;
}

.large-image {
  max-width: 100%;
  height: auto;
  cursor: pointer;
  margin: 10px;
  width: 100%;
  height: 100%;
  border-radius: 8px;
  transition: transform 0.3s ease, box-shadow 0.3s ease;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
}

.large-image:hover {
  transform: scale(1.05);
  box-shadow: 0 8px 16px rgba(0, 0, 0, 0.2);
}

.gallery {
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
  padding: 0 20px; 
}

.gallery-item {
  width: calc(20%);
  margin: 20px;
  width: 230px;
  height: 230px;
}

.fullscreen-overlay {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background: rgba(0, 0, 0, 0.8);
  display: flex;
  justify-content: center;
  align-items: center;
  z-index: 999;
}

.image-container {
  position: relative;
  display: flex;
  justify-content: center;
  align-items: center;
  width: 90%;
  height: 90%;
}

.image-container img {
  max-width: 100%;
  max-height: 100%;
}

.close-button {
  position: absolute;
  top: 10px;
  right: 10px;
  background: transparent;
  border: none;
  color: white;
  font-size: 2rem;
  cursor: pointer;
}

.nav-button {
  position: absolute;
  top: 50%;
  background: transparent;
  border: none;
  color: white;
  font-size: 2rem;
  cursor: pointer;
}

.nav-button.prev {
  left: 10px;
}

.nav-button.next {
  right: 10px;
}
</style>