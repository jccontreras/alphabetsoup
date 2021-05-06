<template>
  <ul id="example-1">
    <li v-for="(word) in arraywords" v-bind:key="word">
      {{ word }}
    </li>
  </ul>
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
