<template>
  <div class="container">
    <div class="row">
      <div class="col-sm-2">
        <words-list/>
      </div>
      <div class="col-sm-10">
        <matrix/>
      </div>
    </div>
  </div>
</template>

<script>
import WordsList from '@/components/WordsList.vue';
import Matrix from '@/components/Matrix.vue';

export default {
  name: 'HomeComponent',
  components: {
    WordsList,
    Matrix,
  },
};
</script>

<style scoped>

</style>
