<template>
  <div class="modal">
    <div class="modal-content">
      <span class="close" @click="emit('closeModal')">&times;</span>
      <input v-model="name" placeholder="Ваше имя">
      <input v-model="phoneNumber" placeholder="Ваш номер телефона">
      <button @click="submitOrder">Отправить заказ</button>
      <button @click="emit('closeModal')">Отмена</button>
    </div>
  </div>
</template>

<script setup>
  const emit = defineEmits(['closeModal']);

  const name = ref('');
  const phoneNumber = ref('');

  function submitOrder() {
    alert(`Your name is ${name.value} and your phone number is ${phoneNumber.value}`);
  }
</script>

<style scoped>
.modal {
  display: flex;
  justify-content: center;
  align-items: center;
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-color: rgba(0, 0, 0, 0.5);
  z-index: 9999;
}

.modal-content {
  background-color: white;
  padding: 40px;
  border-radius: 10px;
  position: relative;
}

input {
  margin-bottom: 10px;
  padding: 8px;
  width: 100%;
  box-sizing: border-box;
}

button {
  padding: 10px;
  margin-right: 10px;
  cursor: pointer;
  border: none;
  border-radius: 5px;
}

.close {
  position: absolute;
  top: 10px;
  right: 15px;
  font-size: 20px;
  cursor: pointer;
}

</style>