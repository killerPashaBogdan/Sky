<template>
    <div v-if="isModalOpen" class="modal">
      <div class="modal-content">
        <span class="close" @click="closeModal">&times;</span>
        <input v-model="userName" placeholder="Ваше имя">
        <input v-model="userPhoneNumber" placeholder="Ваш номер телефона">
        <button @click="submitOrder">Отправить заказ</button>
        <button @click="closeModal">Отмена</button>
      </div>
    </div>
  </template>
  
  <script>
  export default {
    props: ['isModalOpen', 'userName', 'userPhoneNumber'],
    methods: {
      closeModal() {
        this.$emit('close');
      },
      submitOrder() {
        this.$emit('submit', { userName: this.userName, userPhoneNumber: this.userPhoneNumber });
      },
    },
  };
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
  }
  
  .modal-content {
    background-color: white;
    padding: 20px;
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
  