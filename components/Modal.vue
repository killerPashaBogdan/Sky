<template>
  <div class="modal" @click="closeModal">
    <div class="modal-content" @click.stop>
      <form @submit.prevent="submitForm">
        <span class="close" @click="emit('closeModal')">&times;</span>
        <h2>Оставить заявку</h2>
        <input v-model="name" placeholder="Ваше имя" required>
        <input v-model="phoneNumber" placeholder="Номер телефона" required type="tel">
        <button type="submit">Отправить заявку</button>
      </form>
    </div>
  </div>
</template>

<script setup>
import { ref } from 'vue';
import axios from 'axios';

const emit = defineEmits(['closeModal']);

const name = ref('');
const phoneNumber = ref('');

const closeModal = () => {
  emit('closeModal');
};

const submitForm = async () => {
  try {
    await axios.post('http://localhost:3000/send-email', {
      name: name.value,
      phoneNumber: phoneNumber.value
    });
    alert('Заявка успешно отправлена');
    closeModal();
  } catch (error) {
    alert('Ошибка при отправке заявки');
  }
};
</script>

<style scoped>
.modal {
  display: flex;
  justify-content: center;
  align-items: center;
  position: fixed;
  text-align: center;
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
  padding: 12px;
  width: 100%;
  box-sizing: border-box;
  border: 1px solid #ccc;
  border-radius: 8px;
}

button {
  background-color: #2163B2;
  color: white;
  border: none;
  cursor: pointer;
  padding: 20px 25px;
  border-radius: 15px;
  margin-top: 10px;
  font-size: 15px;
}
button:hover {
  background-color: #174580;
}

.close {
  position: absolute;
  top: 10px;
  right: 15px;
  font-size: 20px;
  cursor: pointer;
}
@media (max-width: 1200px) {
  .modal-content {
    padding: 15px;
  }
  button {
    padding: 12px 18px;
    font-size: 13px;
  }

}


@media (max-width: 998px) {
  .modal-content {
    padding: 10px;
  }
  button {
    padding: 10px 15px;
    font-size: 12px;
  }

}


@media (max-width: 768px) {
  .modal-content {
    padding: 5px;
  }
  button {
    padding: 8px 10px;
    font-size: 11px;
  }
  h2{
    font-size: 20px;
  }

}

@media (max-width: 480px) {
  .modal-content {
    padding: 5px;
    border-radius: 5px;
  }
  input{
    font-size: 12px ;
    margin-bottom: 10px;
    padding: 10px;
    width: 80%;
  }
 
}
</style>
