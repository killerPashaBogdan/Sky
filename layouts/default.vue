<template>
  <div>
    <Header />
    <Slider />
    <nuxt />
  </div>
</template>

<script>
import Header from '~/components/Header.vue';
import Slider from '~/components/Slider.vue';

export default {
  components: {
    Header,
    Slider,
  },
};
</script>

<style>

</style>
