<template>
  <!-- Container untuk komponen induk -->
  <div class="parent">
    <!-- Judul komponen induk -->
    <h1>Komponen Induk</h1>
    <!-- Container untuk child component -->
    <div class="child-container">
      <!-- Memanggil ChildComponent dan menambahkan event listener untuk data yang dikirimkan -->
      <ChildComponent @data-emitted="handleDataEmitted" />
      <!-- Menampilkan data yang diterima dari child component jika ada -->
      <p v-if="showReceivedData" class="received-data">Data yang Diterima: {{ receivedData }}</p>
    </div>
  </div>
</template>
<script>
import ChildComponent from './ChildComponent.vue';
export default {
  components: {
    ChildComponent,
  },
  data() {
    return {
      receivedData: '', // Menyimpan data yang diterima dari ChildComponent
      showReceivedData: false, // Untuk mengontrol animasi tampilan data yang diterima
    };
  },
  methods: {
    // Method untuk menangani data yang diterima dari ChildComponent
    handleDataEmitted(data) {
      this.receivedData = data; // Menyimpan data yang diterima
      this.showReceivedData = true; // Menampilkan teks dengan animasi
      // Sembunyikan teks setelah beberapa detik
      setTimeout(() => {
        this.showReceivedData = false;
      }, 3000);
    },
  },
};
</script>

<style scoped>
.parent {
  /* Styling untuk komponen induk */
  background: linear-gradient(135deg, #3498db 0%, #6dd5fa 100%);
  padding: 50px;
  border-radius: 15px;
  text-align: center;
  box-shadow: 0 10px 20px rgba(0, 0, 0, 0.1);
}
.child-container {
  /* Styling untuk container child component */
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
}
.received-data {
  /* Styling untuk teks data yang diterima */
  margin-top: 20px;
  font-size: 1.5em;
  color: #fff;
  opacity: 0;
  animation: fadeIn 1s ease-in-out forwards;
}

@keyframes fadeIn {
  /* Animasi fade in */
  from {
    opacity: 0;
    transform: translateY(10px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}
</style>
