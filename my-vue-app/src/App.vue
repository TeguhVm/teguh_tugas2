<template>
  <div id="app":style="{ backgroundImage: `url(${backgroundImage})` }">
    <h1>{{ greeting }}</h1>
    <p>{{ message }}</p>
    <input type="text" v-model="updatedMessage" placeholder="Masukkan pesan baru">
    <button @click="updateMessage" :class="buttonClass" :disabled="isButtonDisabled">Ubah</button>
    <button @click="resetMessage">Reset</button>
    <img :src="imageSrc" alt="Vue Logo" class="vue-logo">
  </div>
</template>

<script>
export default {
  data() {
    return {
      greeting: 'Selamat Datang di Web Sederhana Teguh!',
      message: 'TEGUH VISYAIFUL MUJAB 4C.',
      updatedMessage: '',
      imageSrc: "Logo.png",
    };
  },
  computed: {
    buttonClass() {
      return this.updatedMessage!== ''? 'primary-button' : 'secondary-button';
    },
    isButtonDisabled() {
      return this.updatedMessage === '';
    }
  },
  methods: {
    updateMessage() {
      this.message = this.updatedMessage!== ''? this.updatedMessage : 'Pesan telah diubah!';
      this.updatedMessage = ''; 
    },
    resetMessage() {
      this.message = 'Ini adalah contoh halaman web dengan Vue.js 3.'; 
    }
  }
};
</script>

<style>
#app {
  font-family: Arial, sans-serif;
  text-align: center;
  background-image: url("./assets/sea.jpg");
  background-size: cover;
  width: 100%;
  height: 100%;
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
}

.primary-button {
  background-color: #007bff;
}

.secondary-button {
  background-color: #6c757d;
}

button {
  padding: 10px 20px;
  border: none;
  border-radius: 5px;
  cursor: pointer;
  margin-top: 10px;
}

.vue-logo {
  width: 150px;
  height: auto;
  position: absolute;
  top: 10px;
  left: 10px;
  height: auto;
}
</style>