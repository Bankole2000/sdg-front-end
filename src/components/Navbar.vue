<template>
  <nav class="navbar">
    <ul class="navbar-nav">
      <li class="logo">
        <router-link to="/" class="nav-link">

          <span class="link-text logo-text">Estimator</span>
          <img class="svg" src="../assets/styles/assets/svgs/estimator.svg"
          alt="Covid-19 Estimator Logo">

        </router-link>
      </li>

      <li class="nav-item">
        <router-link to="/" class="nav-link">

          <img class="svg" src="../assets/styles/assets/svgs/home.svg" alt="Home Icon">
          <span class="link-text">Home</span>

        </router-link>
      </li>

      <li class="nav-item">
        <router-link to="/api" class="nav-link">
          <img class="svg" src="../assets/styles/assets/svgs/api.svg" alt="API Icon">
          <span class="link-text">API</span>
        </router-link>
      </li>

      <li class="nav-item">
        <router-link to="/info" class="nav-link">
         <img class="svg" src="../assets/styles/assets/svgs/info.svg" alt="Info Icon">
          <span class="link-text">Info</span>
        </router-link>
      </li>

      <li class="nav-item" id="themeButton">
        <router-link to="/about" class="nav-link">
         <img class="svg" src="../assets/styles/assets/svgs/About.svg" alt="About Icon">
          <span class="link-text">About</span>
        </router-link>
      </li>
    </ul>
  </nav>
</template>
<script>
export default {
  name: 'Navbar',
  data() {
    return {};
  },
};
</script>
<style></style>
