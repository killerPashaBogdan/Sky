<template>
    <div class="phone">     
        <img @click="emit('changeModal')" class="phone-img" src="/Button.png" >
    </div>
</template>

<script setup>
const emit = defineEmits(['changeModal']);
</script>

<style>
.phone {
  position: fixed;
  bottom: 0;
  right: 0;
  z-index: 1;
}

.phone-img {
  position: relative;
  animation: pulse 2s infinite;
}
@keyframes pulse {
    0% {
        transform: scale(1); 
    }
    50% {
        transform: scale(1.2); 
    }
    100% {
        transform: scale(1); 
    }
}
</style>
