<template>
  <div class="Api">
    <Title title="The Estimator API" />
    <main>
      <h4>About Covid-19 Estimator API, JSON vs xml etc</h4>
<pre class="language-js">
<code>export default {
  name: 'Silly Prims JS test'
}</code></pre>
    </main>
  </div>
</template>

<script>
import Vue from 'vue';
import VuePrism from 'vue-prism';
import 'prismjs/themes/prism-tomorrow.css';
import Title from '@/components/Title.vue';

Vue.use(VuePrism);

export default {
  name: 'Api',
  components: {
    Title,
  },
};
</script>

<style>

</style>
