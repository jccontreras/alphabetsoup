<template>
  <div class="home">
    <h1 style="margin-top: 2rem;">Alphabet Soup</h1>
    <h3>Find the instrument's list</h3>
    <home-component/>
  </div>
</template>

<script>
import HomeComponent from '@/components/HomeComponent.vue';

export default {
  name: 'Home',
  components: {
    HomeComponent,
  },
};
</script>
