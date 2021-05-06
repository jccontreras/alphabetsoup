<template>
  <div class="container-fluid">
    <ul class="list-group">
      <li v-for="(word) in arraywords" v-bind:key="word">
        {{ word }}
      </li>
    </ul>
  </div>
</template>

<script>
import * as constants from '../store/constants';

export default {
  name: 'WordsList',
  data() {
    return {
      arraywords: [],
    };
  },
  mounted() {
    this.arraywords = constants.WORDS.split('/');
  },
};
</script>
