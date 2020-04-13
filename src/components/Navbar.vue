<template>
  <nav class="navbar">
    <ul class="navbar-nav">
      <li class="logo">
        <router-link to="/">
        <a class="nav-link">
          <span class="link-text logo-text">Estimator</span>
          <img class="svg" src="../assets/styles/assets/svgs/disease.svg" alt="">
        </a>
        </router-link>
      </li>

      <li class="nav-item">
        <router-link to="/about">
        <a href="#" class="nav-link">
          <img class="svg" src="../assets/styles/assets/svgs/disease.svg" alt="">
          <span class="link-text">Cats</span>
        </a>
        </router-link>
      </li>

      <li class="nav-item">
        <a href="#" class="nav-link">
          <img class="svg" src="../assets/styles/assets/svgs/disease.svg" alt="">
          <span class="link-text">Aliens</span>
        </a>
      </li>

      <li class="nav-item">
        <a href="#" class="nav-link">
         <img class="svg" src="../assets/styles/assets/svgs/disease.svg" alt="">

          <span class="link-text">Space</span>
        </a>
      </li>

      <li class="nav-item">
        <a href="#" class="nav-link">
          <img class="svg" src="../assets/styles/assets/svgs/disease.svg" alt="">

          <span class="link-text">Shuttle</span>
        </a>
      </li>

      <li class="nav-item" id="themeButton">
        <a href="#" class="nav-link">
         <img class="svg" src="../assets/styles/assets/svgs/disease.svg" alt="">

          <span class="link-text">Themify</span>
        </a>
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
