<template>
  <div>
    <Header @change-modal="changeModalVisibility" />
    <Slider/>
    <Phone  @change-modal="changeModalVisibility" />
    <Transition name="fade">
      <Modal v-if="isModalOpened" @close-modal="changeModalVisibility" />
    </Transition>
    <Details/>
    <OurSrvices @change-modal="changeModalVisibility"/>
    <Gallery/>
    <Faq/>    
    <Contacts/>
    <Footer/>

  </div>
</template>

<script setup>
import Slider from '~/components/Slider.vue';

const isModalOpened = ref('');

function changeModalVisibility() {
  isModalOpened.value = !isModalOpened.value;
}
</script>
<style>
body{
  margin: 0;
  font-family:Tahoma
}
html {
  scroll-behavior: smooth;
}
</style>