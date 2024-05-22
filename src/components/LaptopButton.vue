<template>
    <div>
      <button @click="sendLaptopInfo">Klik untuk Menampilkan Info Laptop</button>
    </div>
  </template>
  
  <script>
  export default {
    name: "LaptopButton",
    data() {
      return {
        laptopInfo: {
          brand: "Acer",
          model: "Aspire 5",
          price: "Rp 10.000.000"
        }
      };
    },
    methods: {
      sendLaptopInfo() {
        this.$emit('laptop-selected', this.laptopInfo);
      }
    }
  };
  </script>
  
  <style scoped>
  button {
    padding: 10px 20px;
    font-size: 16px;
    background-color: #4CAF50;
    color: white;
    border: none;
    border-radius: 5px;
    cursor: pointer;
  }
  
  button:hover {
    background-color: #45a049;
  }
  </style>
  