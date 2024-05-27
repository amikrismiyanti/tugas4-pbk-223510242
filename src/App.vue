<template>
  <!-- Container utama aplikasi -->
  <div id="app">
    <!-- Memanggil ParentComponent -->
    <ParentComponent />
  </div>
</template>

<script>
import ParentComponent from './components/ParentComponent.vue';

export default {
  components: {
    ParentComponent,
  },
};
</script>

<style>
#app {
  /* Styling untuk container utama aplikasi */
  font-family: 'Arial', sans-serif;
  text-align: center;
  color: #333;
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100vh;
  background: linear-gradient(135deg, #3498db 0%, #6dd5fa 100%);
}
</style>
