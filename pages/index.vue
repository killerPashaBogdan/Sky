<template>
  <div>
    <Header @change-modal="changeModalVisibility" />
    <Slider />
    <Transition name="fade">
      <Modal v-if="isModalOpened" @close-modal="changeModalVisibility" />
    </Transition>
  </div>
</template>

<script setup>
const isModalOpened = ref('');

function changeModalVisibility() {
  isModalOpened.value = !isModalOpened.value;
}
</script>