<template>
  <div>
    <Nav />
    <nuxt />
    <Footer />
  </div>
</template>

<script>
import Nav from '~/layouts/Nav.vue';
import Footer from '~/layouts/Footer.vue';

export default {
  components: {
    Nav,
    Footer
  },
  head: {
    title: 'Client Portal',
    bodyAttrs: {
      class: 'bg-gray-100 font-sans leading-normal tracking-normal'
    }
  }
};
</script>
<style>
.shadow-md {
    box-shadow: 0 4px 6px -1px rgb(220 232 240), 0 2px 4px -1px rgb(225 230 235);
}
</style>
