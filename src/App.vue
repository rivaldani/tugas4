<template>
  <div id="app" class="app-container">
    <LaptopInfo>
      <template #default>
        <div class="slot-content">
          <img src="./assets/laptop-image.jpg" alt="Laptop" class="laptop-image">
          <p>Ini informasi Laptop.</p>
        </div>
      </template>
    </LaptopInfo>
  </div>
</template>

<script>
import LaptopInfo from './components/LaptopInfo.vue';

export default {
  name: 'App',
  components: {
    LaptopInfo
  }
};
</script>

<style scoped>
.app-container {
  max-width: 600px;
  margin: 0 auto;
  padding: 20px;
}

.slot-content {
  margin-top: 20px;
  padding: 20px;
  border-radius: 10px;
  background-color: #f8f8f8;
  box-shadow: 0px 0px 10px rgba(0, 0, 0, 0.1);
  text-align: center;
  font-size: 1.2em;
}
</style>
