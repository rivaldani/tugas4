<template>
    <div class="laptop-display">
      <LaptopButton @laptop-selected="handleLaptopSelected" />
      <form @submit.prevent="submitCustomLaptop" class="laptop-form">
        <h3>Tambahkan Informasi Laptop</h3>
        <div class="form-group">
          <label for="brand">Merk:</label>
          <input type="text" id="brand" v-model="customLaptop.brand" required>
        </div>
        <div class="form-group">
          <label for="model">Model:</label>
          <input type="text" id="model" v-model="customLaptop.model" required>
        </div>
        <div class="form-group">
          <label for="price">Harga:</label>
          <input type="text" id="price" v-model="customLaptop.price" required>
        </div>
        <button type="submit">Tambahkan Laptop</button>
      </form>
    </div>
  </template>
  
  <script>
  import LaptopButton from './LaptopButton.vue';
  
  export default {
    name: "LaptopDisplay",
    components: {
      LaptopButton
    },
    data() {
      return {
        customLaptop: {
          brand: '',
          model: '',
          price: ''
        }
      };
    },
    methods: {
      handleLaptopSelected(laptopInfo) {
        this.$emit('laptop-selected', laptopInfo);
      },
      submitCustomLaptop() {
        this.$emit('laptop-selected', this.customLaptop);
        this.customLaptop = { brand: '', model: '', price: '' };
      }
    }
  };
  </script>
  
  <style scoped>
  .laptop-display {
    margin: 20px 0;
  }
  
  .laptop-form {
    margin-top: 20px;
    padding: 20px;
    border: 1px solid #ccc;
    border-radius: 5px;
    background-color: #f9f9f9;
  }
  
  .form-group {
    margin-bottom: 15px;
  }
  
  label {
    display: block;
    font-weight: bold;
  }
  
  input {
    width: 100%;
    padding: 8px;
    font-size: 14px;
    border: 1px solid #ccc;
    border-radius: 3px;
  }
  
  button {
    padding: 8px 15px;
    font-size: 14px;
    background-color: #5c3216;
    color: white;
    border: none;
    border-radius: 3px;
    cursor: pointer;
  }
  
  button:hover {
    background-color: #834f2d;
  }
  </style>
  