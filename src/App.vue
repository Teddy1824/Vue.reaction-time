<template>
  <img alt="Vue logo" src="./assets/logo.png">
 <h1>Bongani's Reaction Timer</h1>
 <button id="play" @click="start" :disabled="isPlaying">Play</button>
<Block v-if="isPlaying" :delay="delay" @done="endGame"/>
<Results v-if="showResults" :score="score" />
</template>

<script>
import Block from './components/Block.vue';
import Results from './components/Results.vue';
export default {
  name: 'App',
  components: {
    Block,
    Results
  },

  data() {
    return {
      isPlaying: false,
      delay: null,
      score: null,
      showResults: false
    }
  },

  methods: {
    start() {
      this.delay = 2000 + Math.random() * 5000;
      this.isPlaying = true;
      this.showResults = false;
    },

    endGame(reactionTime) {
      this.score = reactionTime;
      this.isPlaying = false;
      this.showResults = true;
    }
  },
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #444;
  margin-top: 60px;
}

body {
  background-image: url(https://images.unsplash.com/37/tEREUy1vSfuSu8LzTop3_IMG_2538.jpg?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=1170&q=80);
  background-size: cover;
  background-repeat: no-repeat;
  object-fit: cover;
}
</style>
