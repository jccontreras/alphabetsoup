<template>
  <div class="container-fluid">
    <span @click="buildSoup" style="margin-left: 40rem;">
      Stir Alphabet Soup
      <img src="@/assets/reloadicon.png" style="max-height: 30px; max-width: 30px">
    </span>
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
      while (index < 20) {
        let index2 = 0;
        this.arraywords[index] = [];
        while (index2 < 20) {
          // eslint-disable-next-line max-len
          const result = constant.ALPHABET.charAt(Math.floor(Math.random() * constant.ALPHABET.length));
          this.arraywords[index][index2] = result;
          index2 += 1;
        }
        index += 1;
      }
      const array = constant.WORDS.split('/');
      // eslint-disable-next-line guard-for-in,no-restricted-syntax
      for (const word in array) {
        this.insertWordsList(array[word]);
      }
    },
    insertWordsList(word) {
      const wordarray = word.split('');
      let index = 0;
      const direction = constant.DIRECTION.charAt(Math.floor(
        Math.random() * constant.DIRECTION.length,
      ));
      if (direction === 'V') {
        let y = Math.floor(Math.random() * 20);
        if (y <= 10) {
          const x = Math.floor(Math.random() * 20);
          while (index < wordarray.length) {
            this.arraywords[y][x] = wordarray[index];
            y += 1;
            index += 1;
          }
        } else {
          const x = Math.floor(Math.random() * 20);
          while (index < wordarray.length) {
            this.arraywords[y][x] = wordarray[index];
            y -= 1;
            index += 1;
          }
        }
      } else if (direction === 'H') {
        let x = Math.floor(Math.random() * 20);
        if (x <= 10) {
          const y = Math.floor(Math.random() * 20);
          while (index < wordarray.length) {
            this.arraywords[y][x] = wordarray[index];
            x += 1;
            index += 1;
          }
        } else {
          const y = Math.floor(Math.random() * 20);
          while (index < wordarray.length) {
            this.arraywords[y][x] = wordarray[index];
            x -= 1;
            index += 1;
          }
        }
      } else if (direction === 'D') {
        let x = Math.floor(Math.random() * 20);
        let y = Math.floor(Math.random() * 20);
        if (x <= 10 && y <= 10) {
          while (index < wordarray.length) {
            this.arraywords[y][x] = wordarray[index];
            x += 1;
            y += 1;
            index += 1;
          }
        } else if (x <= 10 && y > 10) {
          while (index < wordarray.length) {
            this.arraywords[y][x] = wordarray[index];
            x += 1;
            y -= 1;
            index += 1;
          }
        } else if (x > 10 && y <= 10) {
          while (index < wordarray.length) {
            this.arraywords[y][x] = wordarray[index];
            x -= 1;
            y += 1;
            index += 1;
          }
        } else if (x > 10 && y > 10) {
          while (index < wordarray.length) {
            this.arraywords[y][x] = wordarray[index];
            x -= 1;
            y -= 1;
            index += 1;
          }
        }
      }
    },
  },
};
</script>
