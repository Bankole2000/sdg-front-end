<template>
  <div id="app">
    <Navbar />
    <router-view />
  </div>
</template>
<script>
// import "@/assets/scripts/materialize";
import Navbar from '@/components/Navbar.vue';

// M.AutoInit();

export default {
  name: 'App',
  components: {
    Navbar,
  },
};
</script>

<style>
@import './assets/styles/main.css';
</style>
