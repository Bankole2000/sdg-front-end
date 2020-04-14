<template>
  <div class="footer">
    <p class="footer-text">Copyright &copy; {{year}} {{owner}} </p>
  </div>
</template>

<script>
export default {
  name: 'Footer',
  data() {
    return {
      owner: 'Bankole',
      year: 2020,
    };
  },
};
</script>

<style>

</style>
