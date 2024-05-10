<template>
  <div class="home">
    <!-- Left Part: Calculator -->
    <div class="calculator-container">
      <HelloWorld/>
    </div>

    <!-- Right Part: Logo and Text -->
    <div class="right-container">
      <img src="@/assets/logo.png" alt="Logo" class="logo">
      <p class="hello-text">This is Calculator built using Vue </p>
    </div>
  </div>
</template>

<script>
import HelloWorld from '@/components/HelloWorld.vue'

export default {
  name: 'HomeView',
  components: {
    HelloWorld
  }
}
</script>

<style scoped>
.home {
  display: flex;
}

.calculator-container {
  flex: 1;
}

.right-container {
  flex: 1;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}

.logo {
  width: 100px; /* Adjust as needed */
  height: auto; /* Adjust as needed */
  margin-bottom: 20px;
}

.hello-text {
  font-size: 24px; /* Adjust as needed */
  color: #333; /* Adjust as needed */
}
</style>
