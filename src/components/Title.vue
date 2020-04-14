<template>
<div class="title">
  <div class="title parallax">
    <strong><h1 class="centered">{{ title }}</h1></strong>
  </div>

</div>


</template>

<script>
export default {
  name: 'Title',
  props: {
    title: String,
  },
  data() {
    return {

    };
  },
};
</script>

<style>
.parallax {
  /* The image used */
  /* background-image: url("../assets/styles/assets/images/title_bg.jpg"); */

  /* Full height */
  height: 30vh;
  margin-top: 0px;
  background: var(--bg-primary);
  /* Create the parallax scrolling effect */
  /* background-attachment: fixed;
  background-position: center;
  background-repeat: no-repeat;
  background-size: cover; */
  z-index: -1;
  position: relative;
  text-align: center;
  color: white;
  display: flex;
  justify-content: space-evenly;
  align-items: center;
}

/* Centered text */
.centered {
  margin-left: 5rem;
  padding: 1rem;
}

@media screen and (max-width: 600px) {
  .centered {
   margin-left: 0;
   padding: 1rem;
  }
}
</style>
