<template>
    <div class="laptop-info">
      <LaptopDisplay @laptop-selected="displayLaptopInfo" />
      <div v-if="selectedLaptop" class="laptop-details">
        <h2>Info Laptop Terpilih:</h2>
        <div class="info">
          <p><span>Merk:</span> {{ selectedLaptop.brand }}</p>
          <p><span>Model:</span> {{ selectedLaptop.model }}</p>
          <p><span>Harga:</span> {{ selectedLaptop.price }}</p>
        </div>
      </div>
      <slot></slot>
    </div>
  </template>
  
  <script>
  import LaptopDisplay from './LaptopDisplay.vue';
  
  export default {
    name: "LaptopInfo",
    components: {
      LaptopDisplay
    },
    data() {
      return {
        selectedLaptop: null
      };
    },
    methods: {
      displayLaptopInfo(laptopInfo) {
        this.selectedLaptop = laptopInfo;
      }
    }
  };
  </script>
  
  <style scoped>
  .laptop-info {
    padding: 20px;
    border: 1px solid #ddd;
    border-radius: 5px;
    background-color: #f9f9f9;
  }
  
  .laptop-details {
    margin-top: 20px;
    padding: 20px;
    border: 1px solid #ccc;
    border-radius: 5px;
    background-color: #fff;
    box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
  }
  
  h2 {
    margin-bottom: 10px;
  }
  
  .info {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 10px;
  }
  
  p {
    margin: 5px 0;
  }
  
  span {
    font-weight: bold;
  }
  </style>
  