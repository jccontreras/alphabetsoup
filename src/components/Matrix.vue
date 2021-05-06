<template>
  <div class="container">
    <div class="row" v-for="(wordh) in arraywords" v-bind:key="wordh"
         style="background-color: aquamarine">
      <div class="col-sm" v-for="(wordv, indexv) in arraywords" v-bind:key="wordv"
           style="border-color: #2c3e50;">
        {{ indexv }}
      </div>
    </div>
  </div>
</template>

<script>
import { WORDS } from '@/store/constants';

export default {
  name: 'Matrix',
  data() {
    return {
      arraywords: [],
    };
  },
  mounted() {
    this.arraywords = WORDS.split('/');
  },
  methods: {
    insertWordsList() {
    },
  },
};
</script>
