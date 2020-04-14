<template>
  <div id="app">
    <Navbar />
    <router-view />
    <Footer />
  </div>
</template>
<script>
// import "@/assets/scripts/materialize";
import Navbar from '@/components/Navbar.vue';
import Footer from '@/components/Footer.vue';

// M.AutoInit();

export default {
  name: 'App',
  components: {
    Navbar,
    Footer,
  },
};
</script>

<style>
@import './assets/styles/main.css';
</style>
