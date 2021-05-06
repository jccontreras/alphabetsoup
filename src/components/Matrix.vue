<template>
  <div class="container">
    <div class="row" v-for="(wordh) in arraywords" v-bind:key="wordh"
         style="background-color: aquamarine">
      <div class="col-sm" v-for="(wordv) in wordh" v-bind:key="wordv">
        {{ wordv }}
      </div>
    </div>
  </div>
</template>

<script>
import * as constant from '@/store/constants';

export default {
  name: 'Matrix',
  data() {
    return {
      arraywords: {
        type: Array,
      },
    };
  },
  mounted() {
    this.buildSoup();
  },
  methods: {
    buildSoup() {
      this.arraywords = [];
      let index = 0;
      while (index < 15) {
        let index2 = 0;
        this.arraywords[index] = [];
        while (index2 < 15) {
          // eslint-disable-next-line max-len
          const result = constant.ALPHABET.charAt(Math.floor(Math.random() * constant.ALPHABET.length));
          this.arraywords[index][index2] = result;
          index2 += 1;
        }
        index += 1;
      }
      const array = constant.WORDS.split('/');
      this.insertWordsList(array[1]);
    },
    insertWordsList(word) {
      const wordarray = word.split('');
      let index = 0;
      // eslint-disable-next-line prefer-destructuring
      // alert(wordarray[0]);
      this.list[4][4] = 'Ñ';
      while (index < wordarray.length) {
        // alert(wordarray[index]);
        index += 1;
      }
    },
  },
};
</script>
