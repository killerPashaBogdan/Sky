<template>
  <section ref="section4" id="section4" class="gallery-section">
    <h1>Галерея работ</h1>
    <div class="gallery">
      <div v-for="(image, index) in galleryImages" :key="index" class="gallery-item">
        <img
          :src="image.src"
          :alt="image.alt"
          loading="lazy"
          class="large-image"
        />
      </div>
    </div>
  </section>
</template>

<script>
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
    };
  },
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
.large-image {
  max-width: 100%;
  height: auto;
  cursor: pointer;
  margin: 10px;
  width: 100%;
  height: 100%;
  border-radius: 8px;
  transition:  0.3s ease, 0.3s ease;
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
  width: calc(100% / 6 - 40px);
  margin: 20px;
  width: 230px;
  height: 230px;
}
</style>