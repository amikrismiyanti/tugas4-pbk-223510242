<template>
    <!-- Container untuk komponen anak -->
    <div class="child">
      <!-- Judul komponen anak -->
      <h2>Komponen Anak</h2>
      <!-- Tombol untuk memicu event dan mengirim data ke parent component -->
      <button @click="emitData" aria-label="Kirim Data">Kirim Data</button>
    </div>
  </template>

  <script>
  export default {
    data() {
      return {
        emittedData: '', // Menyimpan data yang akan dikirim ke parent component
      };
    },
    methods: {
      // Method untuk mengirim data ke parent component
      emitData() {
        const data = 'Kata Anak HALLO!'; // Data yang akan dikirim
        this.emittedData = data; // Menyimpan data yang dikirim
        this.$emit('data-emitted', data); // Memancarkan event dengan data yang dikirim
      },
    },
  };
  </script>
  
  <style scoped>
  .child {
    /* Styling untuk komponen anak */
    background: #fff;
    padding: 30px;
    border-radius: 15px;
    text-align: center;
    box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
  }
  
  button {
    /* Styling untuk tombol */
    background: #4CAF50;
    border: none;
    border-radius: 10px;
    padding: 15px 30px;
    color: #fff;
    cursor: pointer;
    font-size: 1.2em;
  }
  </style>
  